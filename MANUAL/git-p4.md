# git-p4(1) Manual Page

## NAME

git-p4 - Import from and submit to Perforce repositories

## SYNOPSIS

    git p4 clone [<sync options>] [<clone options>] <p4 depot path>…​
    git p4 sync [<sync options>] [<p4 depot path>…​]
    git p4 rebase
    git p4 submit [<submit options>] [<master branch name>]

## DESCRIPTION

This command provides a way to interact with p4 repositories using Git.

Create a new Git repository from an existing p4 repository using _git p4 clone_, giving it one or more p4 depot paths. Incorporate new commits from p4 changes with _git p4 sync_. The _sync_ command is also used to include new branches from other p4 depot paths. Submit Git changes back to p4 using _git p4 submit_. The command _git p4 rebase_ does a sync plus rebases the current branch onto the updated p4 remote branch.

## EXAMPLES

- Clone a repository:

      $ git p4 clone //depot/path/project

- Do some work in the newly created Git repository:

      $ cd project
      $ vi foo.h
      $ git commit -a -m "edited foo.h"

- Update the Git repository with recent changes from p4, rebasing your work on top:

      $ git p4 rebase

- Submit your commits back to p4:

      $ git p4 submit

## COMMANDS

### Clone

Generally, _git p4 clone_ is used to create a new Git directory from an existing p4 repository:

    $ git p4 clone //depot/path/project

This:

1.  Creates an empty Git repository in a subdirectory called _project_.

2.  Imports the full contents of the head revision from the given p4 depot path into a single commit in the Git branch _refs/remotes/p4/master_.

3.  Creates a local branch, _master_ from this remote and checks it out.

To reproduce the entire p4 history in Git, use the _@all_ modifier on the depot path:

    $ git p4 clone //depot/path/project@all

### Sync

As development continues in the p4 repository, those changes can be included in the Git repository using:

    $ git p4 sync

This command finds new changes in p4 and imports them as Git commits.

P4 repositories can be added to an existing Git repository using _git p4 sync_ too:

    $ mkdir repo-git
    $ cd repo-git
    $ git init
    $ git p4 sync //path/in/your/perforce/depot

This imports the specified depot into _refs/remotes/p4/master_ in an existing Git repository. The `--branch` option can be used to specify a different branch to be used for the p4 content.

If a Git repository includes branches _refs/remotes/origin/p4_, these will be fetched and consulted first during a _git p4 sync_. Since importing directly from p4 is considerably slower than pulling changes from a Git remote, this can be useful in a multi-developer environment.

If there are multiple branches, doing _git p4 sync_ will automatically use the "BRANCH DETECTION" algorithm to try to partition new changes into the right branch. This can be overridden with the `--branch` option to specify just a single branch to update.

### Rebase

A common working pattern is to fetch the latest changes from the p4 depot and merge them with local uncommitted changes. Often, the p4 repository is the ultimate location for all code, thus a rebase workflow makes sense. This command does _git p4 sync_ followed by _git rebase_ to move local commits on top of updated p4 changes.

    $ git p4 rebase

### Submit

Submitting changes from a Git repository back to the p4 repository requires a separate p4 client workspace. This should be specified using the `P4CLIENT` environment variable or the Git configuration variable _git-p4.client_. The p4 client must exist, but the client root will be created and populated if it does not already exist.

To submit all changes that are in the current Git branch but not in the _p4/master_ branch, use:

    $ git p4 submit

To specify a branch other than the current one, use:

    $ git p4 submit topicbranch

To specify a single commit or a range of commits, use:

    $ git p4 submit --commit <sha1>
    $ git p4 submit --commit <sha1..sha1>

The upstream reference is generally _refs/remotes/p4/master_, but can be overridden using the `--origin=` command-line option.

The p4 changes will be created as the user invoking _git p4 submit_. The `--preserve-user` option will cause ownership to be modified according to the author of the Git commit. This option requires admin privileges in p4, which can be granted using _p4 protect_.

To shelve changes instead of submitting, use `--shelve` and `--update-shelve`:

    $ git p4 submit --shelve
    $ git p4 submit --update-shelve 1234 --update-shelve 2345

### Unshelve

Unshelving will take a shelved P4 changelist, and produce the equivalent git commit in the branch refs/remotes/p4-unshelved/&lt;changelist&gt;.

The git commit is created relative to the current origin revision (HEAD by default). A parent commit is created based on the origin, and then the unshelve commit is created based on that.

The origin revision can be changed with the "--origin" option.

If the target branch in refs/remotes/p4-unshelved already exists, the old one will be renamed.

    $ git p4 sync
    $ git p4 unshelve 12345
    $ git show p4-unshelved/12345
    <submit more changes via p4 to the same files>
    $ git p4 unshelve 12345
    <refuses to unshelve until git is in sync with p4 again>

## OPTIONS

### General options

All commands except clone accept these options.

--git-dir &lt;dir&gt;  
Set the `GIT_DIR` environment variable. See [git(1)](git.html).

-v  
--verbose  
Provide more progress information.

### Sync options

These options can be used in the initial _clone_ as well as in subsequent _sync_ operations.

--branch &lt;ref&gt;  
Import changes into &lt;ref&gt; instead of refs/remotes/p4/master. If &lt;ref&gt; starts with refs/, it is used as is. Otherwise, if it does not start with p4/, that prefix is added.

By default a &lt;ref&gt; not starting with refs/ is treated as the name of a remote-tracking branch (under refs/remotes/). This behavior can be modified using the --import-local option.

The default &lt;ref&gt; is "master".

This example imports a new remote "p4/proj2" into an existing Git repository:

        $ git init
        $ git p4 sync --branch=refs/remotes/p4/proj2 //depot/proj2

--detect-branches  
Use the branch detection algorithm to find new paths in p4. It is documented below in "BRANCH DETECTION".

--changesfile &lt;file&gt;  
Import exactly the p4 change numbers listed in _file_, one per line. Normally, _git p4_ inspects the current p4 repository state and detects the changes it should import.

--silent  
Do not print any progress information.

--detect-labels  
Query p4 for labels associated with the depot paths, and add them as tags in Git. Limited usefulness as only imports labels associated with new changelists. Deprecated.

--import-labels  
Import labels from p4 into Git.

--import-local  
By default, p4 branches are stored in _refs/remotes/p4/_, where they will be treated as remote-tracking branches by [git-branch(1)](git-branch.html) and other commands. This option instead puts p4 branches in _refs/heads/p4/_. Note that future sync operations must specify `--import-local` as well so that they can find the p4 branches in refs/heads.

--max-changes &lt;n&gt;  
Import at most _n_ changes, rather than the entire range of changes included in the given revision specifier. A typical usage would be use _@all_ as the revision specifier, but then to use _--max-changes 1000_ to import only the last 1000 revisions rather than the entire revision history.

--changes-block-size &lt;n&gt;  
The internal block size to use when converting a revision specifier such as _@all_ into a list of specific change numbers. Instead of using a single call to _p4 changes_ to find the full list of changes for the conversion, there are a sequence of calls to _p4 changes -m_, each of which requests one block of changes of the given size. The default block size is 500, which should usually be suitable.

--keep-path  
The mapping of file names from the p4 depot path to Git, by default, involves removing the entire depot path. With this option, the full p4 depot path is retained in Git. For example, path _//depot/main/foo/bar.c_, when imported from _//depot/main/_, becomes _foo/bar.c_. With `--keep-path`, the Git path is instead _depot/main/foo/bar.c_.

--use-client-spec  
Use a client spec to find the list of interesting files in p4. See the "CLIENT SPEC" section below.

-/ &lt;path&gt;  
Exclude selected depot paths when cloning or syncing.

### Clone options

These options can be used in an initial _clone_, along with the _sync_ options described above.

--destination &lt;directory&gt;  
Where to create the Git repository. If not provided, the last component in the p4 depot path is used to create a new directory.

--bare  
Perform a bare clone. See [git-clone(1)](git-clone.html).

### Submit options

These options can be used to modify _git p4 submit_ behavior.

--origin &lt;commit&gt;  
Upstream location from which commits are identified to submit to p4. By default, this is the most recent p4 commit reachable from `HEAD`.

-M  
Detect renames. See [git-diff(1)](git-diff.html). Renames will be represented in p4 using explicit _move_ operations. There is no corresponding option to detect copies, but there are variables for both moves and copies.

--preserve-user  
Re-author p4 changes before submitting to p4. This option requires p4 admin privileges.

--export-labels  
Export tags from Git as p4 labels. Tags found in Git are applied to the perforce working directory.

-n  
--dry-run  
Show just what commits would be submitted to p4; do not change state in Git or p4.

--prepare-p4-only  
Apply a commit to the p4 workspace, opening, adding and deleting files in p4 as for a normal submit operation. Do not issue the final "p4 submit", but instead print a message about how to submit manually or revert. This option always stops after the first (oldest) commit. Git tags are not exported to p4.

--shelve  
Instead of submitting create a series of shelved changelists. After creating each shelve, the relevant files are reverted/deleted. If you have multiple commits pending multiple shelves will be created.

--update-shelve CHANGELIST  
Update an existing shelved changelist with this commit. Implies --shelve. Repeat for multiple shelved changelists.

--conflict=(ask|skip|quit)  
Conflicts can occur when applying a commit to p4. When this happens, the default behavior ("ask") is to prompt whether to skip this commit and continue, or quit. This option can be used to bypass the prompt, causing conflicting commits to be automatically skipped, or to quit trying to apply commits, without prompting.

--branch &lt;branch&gt;  
After submitting, sync this named branch instead of the default p4/master. See the "Sync options" section above for more information.

--commit &lt;sha1&gt;|&lt;sha1..sha1&gt;  
Submit only the specified commit or range of commits, instead of the full list of changes that are in the current Git branch.

--disable-rebase  
Disable the automatic rebase after all commits have been successfully submitted. Can also be set with git-p4.disableRebase.

--disable-p4sync  
Disable the automatic sync of p4/master from Perforce after commits have been submitted. Implies --disable-rebase. Can also be set with git-p4.disableP4Sync. Sync with origin/master still goes ahead if possible.

## Hooks for submit

### p4-pre-submit

The `p4-pre-submit` hook is executed if it exists and is executable. The hook takes no parameters and nothing from standard input. Exiting with non-zero status from this script prevents `git-p4 submit` from launching. It can be bypassed with the `--no-verify` command line option.

One usage scenario is to run unit tests in the hook.

### p4-prepare-changelist

The `p4-prepare-changelist` hook is executed right after preparing the default changelist message and before the editor is started. It takes one parameter, the name of the file that contains the changelist text. Exiting with a non-zero status from the script will abort the process.

The purpose of the hook is to edit the message file in place, and it is not suppressed by the `--no-verify` option. This hook is called even if `--prepare-p4-only` is set.

### p4-changelist

The `p4-changelist` hook is executed after the changelist message has been edited by the user. It can be bypassed with the `--no-verify` option. It takes a single parameter, the name of the file that holds the proposed changelist text. Exiting with a non-zero status causes the command to abort.

The hook is allowed to edit the changelist file and can be used to normalize the text into some project standard format. It can also be used to refuse the Submit after inspect the message file.

### p4-post-changelist

The `p4-post-changelist` hook is invoked after the submit has successfully occurred in P4. It takes no parameters and is meant primarily for notification and cannot affect the outcome of the git p4 submit action.

### Rebase options

These options can be used to modify _git p4 rebase_ behavior.

--import-labels  
Import p4 labels.

### Unshelve options

--origin  
Sets the git refspec against which the shelved P4 changelist is compared. Defaults to p4/master.

## DEPOT PATH SYNTAX

The p4 depot path argument to _git p4 sync_ and _git p4 clone_ can be one or more space-separated p4 depot paths, with an optional p4 revision specifier on the end:

"//depot/my/project"  
Import one commit with all files in the _\#head_ change under that tree.

"//depot/my/project@all"  
Import one commit for each change in the history of that depot path.

"//depot/my/project@1,6"  
Import only changes 1 through 6.

"//depot/proj1@all //depot/proj2@all"  
Import all changes from both named depot paths into a single repository. Only files below these directories are included. There is not a subdirectory in Git for each "proj1" and "proj2". You must use the `--destination` option when specifying more than one depot path. The revision specifier must be specified identically on each depot path. If there are files in the depot paths with the same name, the path with the most recently updated version of the file is the one that appears in Git.

See _p4 help revisions_ for the full syntax of p4 revision specifiers.

## CLIENT SPEC

The p4 client specification is maintained with the _p4 client_ command and contains among other fields, a View that specifies how the depot is mapped into the client repository. The _clone_ and _sync_ commands can consult the client spec when given the `--use-client-spec` option or when the useClientSpec variable is true. After _git p4 clone_, the useClientSpec variable is automatically set in the repository configuration file. This allows future _git p4 submit_ commands to work properly; the submit command looks only at the variable and does not have a command-line option.

The full syntax for a p4 view is documented in _p4 help views_. _git p4_ knows only a subset of the view syntax. It understands multi-line mappings, overlays with _+_, exclusions with _-_ and double-quotes around whitespace. Of the possible wildcards, _git p4_ only handles _…​_, and only when it is at the end of the path. _git p4_ will complain if it encounters an unhandled wildcard.

Bugs in the implementation of overlap mappings exist. If multiple depot paths map through overlays to the same location in the repository, _git p4_ can choose the wrong one. This is hard to solve without dedicating a client spec just for _git p4_.

The name of the client can be given to _git p4_ in multiple ways. The variable _git-p4.client_ takes precedence if it exists. Otherwise, normal p4 mechanisms of determining the client are used: environment variable `P4CLIENT`, a file referenced by `P4CONFIG`, or the local host name.

## BRANCH DETECTION

P4 does not have the same concept of a branch as Git. Instead, p4 organizes its content as a directory tree, where by convention different logical branches are in different locations in the tree. The _p4 branch_ command is used to maintain mappings between different areas in the tree, and indicate related content. _git p4_ can use these mappings to determine branch relationships.

If you have a repository where all the branches of interest exist as subdirectories of a single depot path, you can use `--detect-branches` when cloning or syncing to have _git p4_ automatically find subdirectories in p4, and to generate these as branches in Git.

For example, if the P4 repository structure is:

    //depot/main/...
    //depot/branch1/...

And "p4 branch -o branch1" shows a View line that looks like:

    //depot/main/... //depot/branch1/...

Then this _git p4 clone_ command:

    git p4 clone --detect-branches //depot@all

produces a separate branch in _refs/remotes/p4/_ for //depot/main, called _master_, and one for //depot/branch1 called _depot/branch1_.

However, it is not necessary to create branches in p4 to be able to use them like branches. Because it is difficult to infer branch relationships automatically, a Git configuration setting _git-p4.branchList_ can be used to explicitly identify branch relationships. It is a list of "source:destination" pairs, like a simple p4 branch specification, where the "source" and "destination" are the path elements in the p4 repository. The example above relied on the presence of the p4 branch. Without p4 branches, the same result will occur with:

    git init depot
    cd depot
    git config git-p4.branchList main:branch1
    git p4 clone --detect-branches //depot@all .

## PERFORMANCE

The fast-import mechanism used by _git p4_ creates one pack file for each invocation of _git p4 sync_. Normally, Git garbage compression ([git-gc(1)](git-gc.html)) automatically compresses these to fewer pack files, but explicit invocation of _git repack -adf_ may improve performance.

## CONFIGURATION VARIABLES

The following config settings can be used to modify _git p4_ behavior. They all are in the _git-p4_ section.

### General variables

git-p4.user  
User specified as an option to all p4 commands, with _-u &lt;user&gt;_. The environment variable `P4USER` can be used instead.

git-p4.password  
Password specified as an option to all p4 commands, with _-P &lt;password&gt;_. The environment variable `P4PASS` can be used instead.

git-p4.port  
Port specified as an option to all p4 commands, with _-p &lt;port&gt;_. The environment variable `P4PORT` can be used instead.

git-p4.host  
Host specified as an option to all p4 commands, with _-h &lt;host&gt;_. The environment variable `P4HOST` can be used instead.

git-p4.client  
Client specified as an option to all p4 commands, with _-c &lt;client&gt;_, including the client spec.

git-p4.retries  
Specifies the number of times to retry a p4 command (notably, _p4 sync_) if the network times out. The default value is 3. Set the value to 0 to disable retries or if your p4 version does not support retries (pre 2012.2).

### Clone and sync variables

git-p4.syncFromOrigin  
Because importing commits from other Git repositories is much faster than importing them from p4, a mechanism exists to find p4 changes first in Git remotes. If branches exist under _refs/remote/origin/p4_, those will be fetched and used when syncing from p4. This variable can be set to _false_ to disable this behavior.

git-p4.branchUser  
One phase in branch detection involves looking at p4 branches to find new ones to import. By default, all branches are inspected. This option limits the search to just those owned by the single user named in the variable.

git-p4.branchList  
List of branches to be imported when branch detection is enabled. Each entry should be a pair of branch names separated by a colon (:). This example declares that both branchA and branchB were created from main:

    git config       git-p4.branchList main:branchA
    git config --add git-p4.branchList main:branchB

git-p4.ignoredP4Labels  
List of p4 labels to ignore. This is built automatically as unimportable labels are discovered.

git-p4.importLabels  
Import p4 labels into git, as per --import-labels.

git-p4.labelImportRegexp  
Only p4 labels matching this regular expression will be imported. The default value is _\[a-zA-Z0-9\_\\-.\]+$_.

git-p4.useClientSpec  
Specify that the p4 client spec should be used to identify p4 depot paths of interest. This is equivalent to specifying the option `--use-client-spec`. See the "CLIENT SPEC" section above. This variable is a boolean, not the name of a p4 client.

git-p4.pathEncoding  
Perforce keeps the encoding of a path as given by the originating OS. Git expects paths encoded as UTF-8. Use this config to tell git-p4 what encoding Perforce had used for the paths. This encoding is used to transcode the paths to UTF-8. As an example, Perforce on Windows often uses "cp1252" to encode path names.

git-p4.largeFileSystem  
Specify the system that is used for large (binary) files. Please note that large file systems do not support the _git p4 submit_ command. Only Git LFS is implemented right now (see <a href="https://git-lfs.github.com/" class="bare">https://git-lfs.github.com/</a> for more information). Download and install the Git LFS command line extension to use this option and configure it like this:

    git config       git-p4.largeFileSystem GitLFS

git-p4.largeFileExtensions  
All files matching a file extension in the list will be processed by the large file system. Do not prefix the extensions with _._.

git-p4.largeFileThreshold  
All files with an uncompressed size exceeding the threshold will be processed by the large file system. By default the threshold is defined in bytes. Add the suffix k, m, or g to change the unit.

git-p4.largeFileCompressedThreshold  
All files with a compressed size exceeding the threshold will be processed by the large file system. This option might slow down your clone/sync process. By default the threshold is defined in bytes. Add the suffix k, m, or g to change the unit.

git-p4.largeFilePush  
Boolean variable which defines if large files are automatically pushed to a server.

git-p4.keepEmptyCommits  
A changelist that contains only excluded files will be imported as an empty commit if this boolean option is set to true.

git-p4.mapUser  
Map a P4 user to a name and email address in Git. Use a string with the following format to create a mapping:

    git config --add git-p4.mapUser "p4user = First Last <mail@address.com>"

A mapping will override any user information from P4. Mappings for multiple P4 user can be defined.

### Submit variables

git-p4.detectRenames  
Detect renames. See [git-diff(1)](git-diff.html). This can be true, false, or a score as expected by _git diff -M_.

git-p4.detectCopies  
Detect copies. See [git-diff(1)](git-diff.html). This can be true, false, or a score as expected by _git diff -C_.

git-p4.detectCopiesHarder  
Detect copies harder. See [git-diff(1)](git-diff.html). A boolean.

git-p4.preserveUser  
On submit, re-author changes to reflect the Git author, regardless of who invokes _git p4 submit_.

git-p4.allowMissingP4Users  
When _preserveUser_ is true, _git p4_ normally dies if it cannot find an author in the p4 user map. This setting submits the change regardless.

git-p4.skipSubmitEdit  
The submit process invokes the editor before each p4 change is submitted. If this setting is true, though, the editing step is skipped.

git-p4.skipSubmitEditCheck  
After editing the p4 change message, _git p4_ makes sure that the description really was changed by looking at the file modification time. This option disables that test.

git-p4.allowSubmit  
By default, any branch can be used as the source for a _git p4 submit_ operation. This configuration variable, if set, permits only the named branches to be used as submit sources. Branch names must be the short names (no "refs/heads/"), and should be separated by commas (","), with no spaces.

git-p4.skipUserNameCheck  
If the user running _git p4 submit_ does not exist in the p4 user map, _git p4_ exits. This option can be used to force submission regardless.

git-p4.attemptRCSCleanup  
If enabled, _git p4 submit_ will attempt to cleanup RCS keywords ($Header$, etc). These would otherwise cause merge conflicts and prevent the submit going ahead. This option should be considered experimental at present.

git-p4.exportLabels  
Export Git tags to p4 labels, as per --export-labels.

git-p4.labelExportRegexp  
Only p4 labels matching this regular expression will be exported. The default value is _\[a-zA-Z0-9\_\\-.\]+$_.

git-p4.conflict  
Specify submit behavior when a conflict with p4 is found, as per --conflict. The default behavior is _ask_.

git-p4.disableRebase  
Do not rebase the tree against p4/master following a submit.

git-p4.disableP4Sync  
Do not sync p4/master with Perforce following a submit. Implies git-p4.disableRebase.

## IMPLEMENTATION DETAILS

- Changesets from p4 are imported using Git fast-import.

- Cloning or syncing does not require a p4 client; file contents are collected using _p4 print_.

- Submitting requires a p4 client, which is not in the same location as the Git repository. Patches are applied, one at a time, to this p4 client and submitted from there.

- Each commit imported by _git p4_ has a line at the end of the log message indicating the p4 depot location and change number. This line is used by later _git p4 sync_ operations to know which p4 changes are new.
