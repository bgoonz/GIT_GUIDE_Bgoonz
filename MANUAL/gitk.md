# gitk(1) Manual Page

## NAME

gitk - The Git repository browser

## SYNOPSIS

    gitk [<options>] [<revision range>] [--] [<path>…​]

## DESCRIPTION

Displays changes in a repository or a selected set of commits. This includes visualizing the commit graph, showing information related to each commit, and the files in the trees of each revision.

## OPTIONS

To control which revisions to show, gitk supports most options applicable to the _git rev-list_ command. It also supports a few options applicable to the \*git diff-\*\* commands to control how the changes each commit introduces are shown. Finally, it supports some gitk-specific options.

gitk generally only understands options with arguments in the _sticked_ form (see [gitcli(7)](gitcli.html)) due to limitations in the command-line parser.

### rev-list options and arguments

This manual page describes only the most frequently used options. See [git-rev-list(1)](git-rev-list.html) for a complete list.

--all  
Show all refs (branches, tags, etc.).

--branches\[=&lt;pattern&gt;\]  
--tags\[=&lt;pattern&gt;\]  
--remotes\[=&lt;pattern&gt;\]  
Pretend as if all the branches (tags, remote branches, resp.) are listed on the command line as _&lt;commit&gt;_. If _&lt;pattern&gt;_ is given, limit refs to ones matching given shell glob. If pattern lacks _?_, \*\*_, or _\[_, _/\*\* at the end is implied.

--since=&lt;date&gt;  
Show commits more recent than a specific date.

--until=&lt;date&gt;  
Show commits older than a specific date.

--date-order  
Sort commits by date when possible.

--merge  
After an attempt to merge stops with conflicts, show the commits on the history between two branches (i.e. the HEAD and the MERGE_HEAD) that modify the conflicted files and do not exist on all the heads being merged.

--left-right  
Mark which side of a symmetric difference a commit is reachable from. Commits from the left side are prefixed with a `<` symbol and those from the right with a `>` symbol.

--full-history  
When filtering history with _&lt;path&gt;…​_, does not prune some history. (See "History simplification" in [git-log(1)](git-log.html) for a more detailed explanation.)

--simplify-merges  
Additional option to `--full-history` to remove some needless merges from the resulting history, as there are no selected commits contributing to this merge. (See "History simplification" in [git-log(1)](git-log.html) for a more detailed explanation.)

--ancestry-path  
When given a range of commits to display (e.g. _commit1..commit2_ or _commit2 ^commit1_), only display commits that exist directly on the ancestry chain between the _commit1_ and _commit2_, i.e. commits that are both descendants of _commit1_, and ancestors of _commit2_. (See "History simplification" in [git-log(1)](git-log.html) for a more detailed explanation.)

-L&lt;start&gt;,&lt;end&gt;:&lt;file&gt;  
-L:&lt;funcname&gt;:&lt;file&gt;  
Trace the evolution of the line range given by _&lt;start&gt;,&lt;end&gt;_, or by the function name regex _&lt;funcname&gt;_, within the _&lt;file&gt;_. You may not give any pathspec limiters. This is currently limited to a walk starting from a single revision, i.e., you may only give zero or one positive revision arguments, and _&lt;start&gt;_ and _&lt;end&gt;_ (or _&lt;funcname&gt;_) must exist in the starting revision. You can specify this option more than once. Implies `--patch`. Patch output can be suppressed using `--no-patch`, but other diff formats (namely `--raw`, `--numstat`, `--shortstat`, `--dirstat`, `--summary`, `--name-only`, `--name-status`, `--check`) are not currently implemented.

_&lt;start&gt;_ and _&lt;end&gt;_ can take one of these forms:

- number

  If _&lt;start&gt;_ or _&lt;end&gt;_ is a number, it specifies an absolute line number (lines count from 1).

- `/regex/`

  This form will use the first line matching the given POSIX regex. If _&lt;start&gt;_ is a regex, it will search from the end of the previous `-L` range, if any, otherwise from the start of file. If _&lt;start&gt;_ is `^/regex/`, it will search from the start of file. If _&lt;end&gt;_ is a regex, it will search starting at the line given by _&lt;start&gt;_.

- +offset or -offset

  This is only valid for _&lt;end&gt;_ and will specify a number of lines before or after the line given by _&lt;start&gt;_.

If `:<funcname>` is given in place of _&lt;start&gt;_ and _&lt;end&gt;_, it is a regular expression that denotes the range from the first funcname line that matches _&lt;funcname&gt;_, up to the next funcname line. `:<funcname>` searches from the end of the previous `-L` range, if any, otherwise from the start of file. `^:<funcname>` searches from the start of file. The function names are determined in the same way as `git diff` works out patch hunk headers (see _Defining a custom hunk-header_ in [gitattributes(5)](gitattributes.html)).

&lt;revision range&gt;  
Limit the revisions to show. This can be either a single revision meaning show from the given revision and back, or it can be a range in the form "_&lt;from&gt;_.._&lt;to&gt;_" to show all revisions between _&lt;from&gt;_ and back to _&lt;to&gt;_. Note, more advanced revision selection can be applied. For a more complete list of ways to spell object names, see [gitrevisions(7)](gitrevisions.html).

&lt;path&gt;…​  
Limit commits to the ones touching files in the given paths. Note, to avoid ambiguity with respect to revision names use "--" to separate the paths from any preceding options.

### gitk-specific options

--argscmd=&lt;command&gt;  
Command to be run each time gitk has to determine the revision range to show. The command is expected to print on its standard output a list of additional revisions to be shown, one per line. Use this instead of explicitly specifying a _&lt;revision range&gt;_ if the set of commits to show may vary between refreshes.

--select-commit=&lt;ref&gt;  
Select the specified commit after loading the graph. Default behavior is equivalent to specifying _--select-commit=HEAD_.

## Examples

gitk v2.6.12.. include/scsi drivers/scsi  
Show the changes since version _v2.6.12_ that changed any file in the include/scsi or drivers/scsi subdirectories

gitk --since="2 weeks ago" -- gitk  
Show the changes during the last two weeks to the file _gitk_. The "--" is necessary to avoid confusion with the **branch** named _gitk_

gitk --max-count=100 --all -- Makefile  
Show at most 100 changes made to the file _Makefile_. Instead of only looking for changes in the current branch look in all branches.

## Files

User configuration and preferences are stored at:

- `$XDG_CONFIG_HOME/git/gitk` if it exists, otherwise

- `$HOME/.gitk` if it exists

If neither of the above exist then `$XDG_CONFIG_HOME/git/gitk` is created and used by default. If _$XDG_CONFIG_HOME_ is not set it defaults to `$HOME/.config` in all cases.

## History

Gitk was the first graphical repository browser. It’s written in tcl/tk.

_gitk_ is actually maintained as an independent project, but stable versions are distributed as part of the Git suite for the convenience of end users.

gitk-git/ comes from Paul Mackerras’s gitk project:

    git://ozlabs.org/~paulus/gitk

## SEE ALSO

_qgit(1)_  
A repository browser written in C++ using Qt.

_tig(1)_  
A minimal repository browser and Git tool output highlighter written in C using Ncurses.

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
