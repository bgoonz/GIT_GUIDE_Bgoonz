---

**Table of Contents**

<span class="preface">[](#id-1.2)</span>

<span class="chapter">[1. Repositories and Branches](#repositories-and-branches)</span>

<span class="section">[How to get a Git repository](#how-to-get-a-git-repository)</span>

<span class="section">[How to check out a different version of a project](#how-to-check-out)</span>

<span class="section">[Understanding History: Commits](#understanding-commits)</span>

<span class="section">[Understanding history: commits, parents, and reachability](#understanding-reachability)</span>

<span class="section">[Understanding history: History diagrams](#history-diagrams)</span>

<span class="section">[Understanding history: What is a branch?](#what-is-a-branch)</span>

<span class="section">[Manipulating branches](#manipulating-branches)</span>

<span class="section">[Examining an old version without creating a new branch](#detached-head)</span>

<span class="section">[Examining branches from a remote repository](#examining-remote-branches)</span>

<span class="section">[Naming branches, tags, and other references](#how-git-stores-references)</span>

<span class="section">[Updating a repository with git fetch](#Updating-a-repository-With-git-fetch)</span>

<span class="section">[Fetching branches from other repositories](#fetching-branches)</span>

<span class="chapter">[2. Exploring Git history](#exploring-git-history)</span>

<span class="section">[How to use bisect to find a regression](#using-bisect)</span>

<span class="section">[Naming commits](#naming-commits)</span>

<span class="section">[Creating tags](#creating-tags)</span>

<span class="section">[Browsing revisions](#browsing-revisions)</span>

<span class="section">[Generating diffs](#generating-diffs)</span>

<span class="section">[Viewing old file versions](#viewing-old-file-versions)</span>

<span class="section">[Examples](#history-examples)</span>

<span class="section">[Counting the number of commits on a branch](#counting-commits-on-a-branch)</span>

<span class="section">[Check whether two branches point at the same history](#checking-for-equal-branches)</span>

<span class="section">[Find first tagged version including a given fix](#finding-tagged-descendants)</span>

<span class="section">[Showing commits unique to a given branch](#showing-commits-unique-to-a-branch)</span>

<span class="section">[Creating a changelog and tarball for a software release](#making-a-release)</span>

<span class="section">[Finding commits referencing a file with given content](#Finding-commits-With-given-Content)</span>

<span class="chapter">[3. Developing with Git](#Developing-With-git)</span>

<span class="section">[Telling Git your name](#telling-git-your-name)</span>

<span class="section">[Creating a new repository](#creating-a-new-repository)</span>

<span class="section">[How to make a commit](#how-to-make-a-commit)</span>

<span class="section">[Creating good commit messages](#creating-good-commit-messages)</span>

<span class="section">[Ignoring files](#ignoring-files)</span>

<span class="section">[How to merge](#how-to-merge)</span>

<span class="section">[Resolving a merge](#resolving-a-merge)</span>

<span class="section">[Getting conflict-resolution help during a merge](#conflict-resolution)</span>

<span class="section">[Undoing a merge](#undoing-a-merge)</span>

<span class="section">[Fast-forward merges](#fast-forwards)</span>

<span class="section">[Fixing mistakes](#fixing-mistakes)</span>

<span class="section">[Fixing a mistake with a new commit](#reverting-a-commit)</span>

<span class="section">[Fixing a mistake by rewriting history](#fixing-a-mistake-by-rewriting-history)</span>

<span class="section">[Checking out an old version of a file](#checkout-of-path)</span>

<span class="section">[Temporarily setting aside work in progress](#interrupted-work)</span>

<span class="section">[Ensuring good performance](#ensuring-good-performance)</span>

<span class="section">[Ensuring reliability](#ensuring-reliability)</span>

<span class="section">[Checking the repository for corruption](#checking-for-corruption)</span>

<span class="section">[Recovering lost changes](#recovering-lost-changes)</span>

<span class="chapter">[4. Sharing development with others](#sharing-development)</span>

<span class="section">[Getting updates with git pull](#getting-updates-With-git-pull)</span>

<span class="section">[Submitting patches to a project](#submitting-patches)</span>

<span class="section">[Importing patches to a project](#importing-patches)</span>

<span class="section">[Public Git repositories](#public-repositories)</span>

<span class="section">[Setting up a public repository](#setting-up-a-public-repository)</span>

<span class="section">[Exporting a Git repository via the Git protocol](#exporting-via-git)</span>

<span class="section">[Exporting a git repository via HTTP](#exporting-via-http)</span>

<span class="section">[Pushing changes to a public repository](#pushing-changes-to-a-public-repository)</span>

<span class="section">[What to do when a push fails](#forcing-push)</span>

<span class="section">[Setting up a shared repository](#setting-up-a-shared-repository)</span>

<span class="section">[Allowing web browsing of a repository](#setting-up-gitweb)</span>

<span class="section">[How to get a Git repository with minimal history](#how-to-get-a-git-repository-with-minimal-history)</span>

<span class="section">[Examples](#sharing-development-examples)</span>

<span class="section">[Maintaining topic branches for a Linux subsystem maintainer](#maintaining-topic-branches)</span>

<span class="chapter">[5. Rewriting history and maintaining patch series](#cleaning-up-history)</span>

<span class="section">[Creating the perfect patch series](#patch-series)</span>

<span class="section">[Keeping a patch series up to date using git rebase](#using-git-rebase)</span>

<span class="section">[Rewriting a single commit](#rewriting-one-commit)</span>

<span class="section">[Reordering or selecting from a patch series](#reordering-patch-series)</span>

<span class="section">[Using interactive rebases](#interactive-rebase)</span>

<span class="section">[Other tools](#patch-series-tools)</span>

<span class="section">[Problems with rewriting history](#problems-With-rewriting-history)</span>

<span class="section">[Why bisecting merge commits can be harder than bisecting linear history](#bisect-merges)</span>

<span class="chapter">[6. Advanced branch management](#advanced-branch-management)</span>

<span class="section">[Fetching individual branches](#fetching-individual-branches)</span>

<span class="section">[git fetch and fast-forwards](#fetch-fast-forwards)</span>

<span class="section">[Forcing git fetch to do non-fast-forward updates](#forcing-fetch)</span>

<span class="section">[Configuring remote-tracking branches](#remote-branch-configuration)</span>

<span class="chapter">[7. Git concepts](#git-concepts)</span>

<span class="section">[The Object Database](#the-object-database)</span>

<span class="section">[Commit Object](#commit-object)</span>

<span class="section">[Tree Object](#tree-object)</span>

<span class="section">[Blob Object](#blob-object)</span>

<span class="section">[Trust](#trust)</span>

<span class="section">[Tag Object](#tag-object)</span>

<span class="section">[How Git stores objects efficiently: pack files](#pack-files)</span>

<span class="section">[Dangling objects](#dangling-objects)</span>

<span class="section">[Recovering from repository corruption](#recovering-from-repository-corruption)</span>

<span class="section">[The index](#the-index)</span>

<span class="chapter">[8. Submodules](#submodules)</span>

<span class="section">[Pitfalls with submodules](#pitfalls-with-submodules)</span>

<span class="chapter">[9. Low-level Git operations](#low-level-operations)</span>

<span class="section">[Object access and manipulation](#object-manipulation)</span>

<span class="section">[The Workflow](#the-workflow)</span>

<span class="section">[working directory → index](#working-directory-to-index)</span>

<span class="section">[index → object database](#index-to-object-database)</span>

<span class="section">[object database → index](#object-database-to-index)</span>

<span class="section">[index → working directory](#index-to-working-directory)</span>

<span class="section">[Tying it all together](#tying-it-all-together)</span>

<span class="section">[Examining the data](#examining-the-data)</span>

<span class="section">[Merging multiple trees](#merging-multiple-trees)</span>

<span class="section">[Merging multiple trees, continued](#merging-multiple-trees-2)</span>

<span class="chapter">[10. Hacking Git](#hacking-git)</span>

<span class="section">[Object storage format](#object-details)</span>

<span class="section">[A birds-eye view of Git’s source code](#birdview-on-the-source-code)</span>

<span class="chapter">[11. Git Glossary](#glossary)</span>

<span class="section">[Git explained](#git-explained)</span>

<span class="appendix">[A. Git Quick Reference](#git-quick-start)</span>

<span class="section">[Creating a new repository](#quick-creating-a-new-repository)</span>

<span class="section">[Managing branches](#managing-branches)</span>

<span class="section">[Exploring history](#exploring-history)</span>

<span class="section">[Making changes](#making-changes)</span>

<span class="section">[Merging](#merging)</span>

<span class="section">[Sharing your changes](#sharing-your-changes)</span>

<span class="section">[Repository maintenance](#repository-maintenance)</span>

<span class="appendix">[B. Notes and todo list for this manual](#todo)</span>

<span class="section">[Todo list](#todo-list)</span>

Git is a fast distributed revision control system.

This manual is designed to be readable by someone with basic UNIX command-line skills, but no previous knowledge of Git.

<a href="#repositories-and-branches" class="xref" title="Chapter 1. Repositories and Branches">Chapter 1, <em>Repositories and Branches</em></a> and <a href="#exploring-git-history" class="xref" title="Chapter 2. Exploring Git history">Chapter 2, <em>Exploring Git history</em></a> explain how to fetch and study a project using git—​read these chapters to learn how to build and test a particular version of a software project, search for regressions, and so on.

People needing to do actual development will also want to read <a href="#Developing-With-git" class="xref" title="Chapter 3. Developing with Git">Chapter 3, <em>Developing with Git</em></a> and <a href="#sharing-development" class="xref" title="Chapter 4. Sharing development with others">Chapter 4, <em>Sharing development with others</em></a>.

Further chapters cover more specialized topics.

Comprehensive reference documentation is available through the man pages, or <a href="git-help.html" class="ulink">git-help(1)</a> command. For example, for the command `git clone <repo>`, you can either use:

    $ man git-clone

or:

    $ git help clone

With the latter, you can use the manual viewer of your choice; see <a href="git-help.html" class="ulink">git-help(1)</a> for more information.

See also <a href="#git-quick-start" class="xref" title="Appendix A. Git Quick Reference">Appendix A, <em>Git Quick Reference</em></a> for a brief overview of Git commands, without any explanation.

Finally, see <a href="#todo" class="xref" title="Appendix B. Notes and todo list for this manual">Appendix B, <em>Notes and todo list for this manual</em></a> for ways that you can help make this manual more complete.

**Table of Contents**

<span class="section">[How to get a Git repository](#how-to-get-a-git-repository)</span>

<span class="section">[How to check out a different version of a project](#how-to-check-out)</span>

<span class="section">[Understanding History: Commits](#understanding-commits)</span>

<span class="section">[Understanding history: commits, parents, and reachability](#understanding-reachability)</span>

<span class="section">[Understanding history: History diagrams](#history-diagrams)</span>

<span class="section">[Understanding history: What is a branch?](#what-is-a-branch)</span>

<span class="section">[Manipulating branches](#manipulating-branches)</span>

<span class="section">[Examining an old version without creating a new branch](#detached-head)</span>

<span class="section">[Examining branches from a remote repository](#examining-remote-branches)</span>

<span class="section">[Naming branches, tags, and other references](#how-git-stores-references)</span>

<span class="section">[Updating a repository with git fetch](#Updating-a-repository-With-git-fetch)</span>

<span class="section">[Fetching branches from other repositories](#fetching-branches)</span>

## <span id="how-to-get-a-git-repository"></span>How to get a Git repository

It will be useful to have a Git repository to experiment with as you read this manual.

The best way to get one is by using the <a href="git-clone.html" class="ulink">git-clone(1)</a> command to download a copy of an existing repository. If you don’t already have a project in mind, here are some interesting examples:

            # Git itself (approx. 40MB download):
    $ git clone git://git.kernel.org/pub/scm/git/git.git
            # the Linux kernel (approx. 640MB download):
    $ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git

The initial clone may be time-consuming for a large project, but you will only need to clone once.

The clone command creates a new directory named after the project (`git` or `linux` in the examples above). After you cd into this directory, you will see that it contains a copy of the project files, called the <a href="#def_working_tree" class="link">working tree</a>, together with a special top-level directory named `.git`, which contains all the information about the history of the project.

## <span id="how-to-check-out"></span>How to check out a different version of a project

Git is best thought of as a tool for storing the history of a collection of files. It stores the history as a compressed collection of interrelated snapshots of the project’s contents. In Git each such version is called a <a href="#def_commit" class="link">commit</a>.

Those snapshots aren’t necessarily all arranged in a single line from oldest to newest; instead, work may simultaneously proceed along parallel lines of development, called <a href="#def_branch" class="link">branches</a>, which may merge and diverge.

A single Git repository can track development on multiple branches. It does this by keeping a list of <a href="#def_head" class="link">heads</a> which reference the latest commit on each branch; the <a href="git-branch.html" class="ulink">git-branch(1)</a> command shows you the list of branch heads:

    $ git branch
    * master

A freshly cloned repository contains a single branch head, by default named "master", with the working directory initialized to the state of the project referred to by that branch head.

Most projects also use <a href="#def_tag" class="link">tags</a>. Tags, like heads, are references into the project’s history, and can be listed using the <a href="git-tag.html" class="ulink">git-tag(1)</a> command:

    $ git tag -l
    v2.6.11
    v2.6.11-tree
    v2.6.12
    v2.6.12-rc2
    v2.6.12-rc3
    v2.6.12-rc4
    v2.6.12-rc5
    v2.6.12-rc6
    v2.6.13
    ...

Tags are expected to always point at the same version of a project, while heads are expected to advance as development progresses.

Create a new branch head pointing to one of these versions and check it out using <a href="git-switch.html" class="ulink">git-switch(1)</a>:

    $ git switch -c new v2.6.13

The working directory then reflects the contents that the project had when it was tagged v2.6.13, and <a href="git-branch.html" class="ulink">git-branch(1)</a> shows two branches, with an asterisk marking the currently checked-out branch:

    $ git branch
      master
    * new

If you decide that you’d rather see version 2.6.17, you can modify the current branch to point at v2.6.17 instead, with

    $ git reset --hard v2.6.17

Note that if the current branch head was your only reference to a particular point in history, then resetting that branch may leave you with no way to find the history it used to point to; so use this command carefully.

## <span id="understanding-commits"></span>Understanding History: Commits

Every change in the history of a project is represented by a commit. The <a href="git-show.html" class="ulink">git-show(1)</a> command shows the most recent commit on the current branch:

    $ git show
    commit 17cf781661e6d38f737f15f53ab552f1e95960d7
    Author: Linus Torvalds <torvalds@ppc970.osdl.org.(none)>
    Date:   Tue Apr 19 14:11:06 2005 -0700

        Remove duplicate getenv(DB_ENVIRONMENT) call

        Noted by Tony Luck.

    diff --git a/init-db.c b/init-db.c
    index 65898fa..b002dc6 100644
    --- a/init-db.c
    +++ b/init-db.c
    @@ -7,7 +7,7 @@

     int main(int argc, char **argv)
     {
    -       char *sha1_dir = getenv(DB_ENVIRONMENT), *path;
    +       char *sha1_dir, *path;
            int len, i;

            if (mkdir(".git", 0755) < 0) {

As you can see, a commit shows who made the latest change, what they did, and why.

Every commit has a 40-hexdigit id, sometimes called the "object name" or the "SHA-1 id", shown on the first line of the `git show` output. You can usually refer to a commit by a shorter name, such as a tag or a branch name, but this longer name can also be useful. Most importantly, it is a globally unique name for this commit: so if you tell somebody else the object name (for example in email), then you are guaranteed that name will refer to the same commit in their repository that it does in yours (assuming their repository has that commit at all). Since the object name is computed as a hash over the contents of the commit, you are guaranteed that the commit can never change without its name also changing.

In fact, in <a href="#git-concepts" class="xref" title="Chapter 7. Git concepts">Chapter 7, <em>Git concepts</em></a> we shall see that everything stored in Git history, including file data and directory contents, is stored in an object with a name that is a hash of its contents.

### <span id="understanding-reachability"></span>Understanding history: commits, parents, and reachability

Every commit (except the very first commit in a project) also has a parent commit which shows what happened before this commit. Following the chain of parents will eventually take you back to the beginning of the project.

However, the commits do not form a simple list; Git allows lines of development to diverge and then reconverge, and the point where two lines of development reconverge is called a "merge". The commit representing a merge can therefore have more than one parent, with each parent representing the most recent commit on one of the lines of development leading to that point.

The best way to see how this works is using the <a href="gitk.html" class="ulink">gitk(1)</a> command; running gitk now on a Git repository and looking for merge commits will help understand how Git organizes history.

In the following, we say that commit X is "reachable" from commit Y if commit X is an ancestor of commit Y. Equivalently, you could say that Y is a descendant of X, or that there is a chain of parents leading from commit Y to commit X.

### <span id="history-diagrams"></span>Understanding history: History diagrams

We will sometimes represent Git history using diagrams like the one below. Commits are shown as "o", and the links between them with lines drawn with - / and \\. Time goes left to right:

             o--o--o <-- Branch A
            /
     o--o--o <-- master
            \
             o--o--o <-- Branch B

If we need to talk about a particular commit, the character "o" may be replaced with another letter or number.

### <span id="what-is-a-branch"></span>Understanding history: What is a branch?

When we need to be precise, we will use the word "branch" to mean a line of development, and "branch head" (or just "head") to mean a reference to the most recent commit on a branch. In the example above, the branch head named "A" is a pointer to one particular commit, but we refer to the line of three commits leading up to that point as all being part of "branch A".

However, when no confusion will result, we often just use the term "branch" both for branches and for branch heads.

## <span id="manipulating-branches"></span>Manipulating branches

Creating, deleting, and modifying branches is quick and easy; here’s a summary of the commands:

<span class="term">`git branch`</span>  
list all branches.

<span class="term">`git branch <branch>`</span>  
create a new branch named `<branch>`, referencing the same point in history as the current branch.

<span class="term">`git branch <branch> <start-point>`</span>  
create a new branch named `<branch>`, referencing `<start-point>`, which may be specified any way you like, including using a branch name or a tag name.

<span class="term">`git branch -d <branch>`</span>  
delete the branch `<branch>`; if the branch is not fully merged in its upstream branch or contained in the current branch, this command will fail with a warning.

<span class="term">`git branch -D <branch>`</span>  
delete the branch `<branch>` irrespective of its merged status.

<span class="term">`git switch <branch>`</span>  
make the current branch `<branch>`, updating the working directory to reflect the version referenced by `<branch>`.

<span class="term">`git switch -c <new> <start-point>`</span>  
create a new branch `<new>` referencing `<start-point>`, and check it out.

The special symbol "HEAD" can always be used to refer to the current branch. In fact, Git uses a file named `HEAD` in the `.git` directory to remember which branch is current:

    $ cat .git/HEAD
    ref: refs/heads/master

## <span id="detached-head"></span>Examining an old version without creating a new branch

The `git switch` command normally expects a branch head, but will also accept an arbitrary commit when invoked with --detach; for example, you can check out the commit referenced by a tag:

    $ git switch --detach v2.6.17
    Note: checking out 'v2.6.17'.

    You are in 'detached HEAD' state. You can look around, make experimental
    changes and commit them, and you can discard any commits you make in this
    state without impacting any branches by performing another switch.

    If you want to create a new branch to retain commits you create, you may
    do so (now or later) by using -c with the switch command again. Example:

      git switch -c new_branch_name

    HEAD is now at 427abfa Linux v2.6.17

The HEAD then refers to the SHA-1 of the commit instead of to a branch, and git branch shows that you are no longer on a branch:

    $ cat .git/HEAD
    427abfa28afedffadfca9dd8b067eb6d36bac53f
    $ git branch
    * (detached from v2.6.17)
      master

In this case we say that the HEAD is "detached".

This is an easy way to check out a particular version without having to make up a name for the new branch. You can still create a new branch (or tag) for this version later if you decide to.

## <span id="examining-remote-branches"></span>Examining branches from a remote repository

The "master" branch that was created at the time you cloned is a copy of the HEAD in the repository that you cloned from. That repository may also have had other branches, though, and your local repository keeps branches which track each of those remote branches, called remote-tracking branches, which you can view using the `-r` option to <a href="git-branch.html" class="ulink">git-branch(1)</a>:

    $ git branch -r
      origin/HEAD
      origin/html
      origin/maint
      origin/man
      origin/master
      origin/next
      origin/seen
      origin/todo

In this example, "origin" is called a remote repository, or "remote" for short. The branches of this repository are called "remote branches" from our point of view. The remote-tracking branches listed above were created based on the remote branches at clone time and will be updated by `git fetch` (hence `git pull`) and `git push`. See <a href="#Updating-a-repository-With-git-fetch" class="xref" title="Updating a repository with git fetch">the section called “Updating a repository with git fetch”</a> for details.

You might want to build on one of these remote-tracking branches on a branch of your own, just as you would for a tag:

    $ git switch -c my-todo-copy origin/todo

You can also check out `origin/todo` directly to examine it or write a one-off patch. See <a href="#detached-head" class="link" title="Examining an old version without creating a new branch">detached head</a>.

Note that the name "origin" is just the name that Git uses by default to refer to the repository that you cloned from.

## <span id="how-git-stores-references"></span>Naming branches, tags, and other references

Branches, remote-tracking branches, and tags are all references to commits. All references are named with a slash-separated path name starting with `refs`; the names we’ve been using so far are actually shorthand:

- The branch `test` is short for `refs/heads/test`.
- The tag `v2.6.18` is short for `refs/tags/v2.6.18`.
- `origin/master` is short for `refs/remotes/origin/master`.

The full name is occasionally useful if, for example, there ever exists a tag and a branch with the same name.

(Newly created refs are actually stored in the `.git/refs` directory, under the path given by their name. However, for efficiency reasons they may also be packed together in a single file; see <a href="git-pack-refs.html" class="ulink">git-pack-refs(1)</a>).

As another useful shortcut, the "HEAD" of a repository can be referred to just using the name of that repository. So, for example, "origin" is usually a shortcut for the HEAD branch in the repository "origin".

For the complete list of paths which Git checks for references, and the order it uses to decide which to choose when there are multiple references with the same shorthand name, see the "SPECIFYING REVISIONS" section of <a href="gitrevisions.html" class="ulink">gitrevisions(7)</a>.

## <span id="Updating-a-repository-With-git-fetch"></span>Updating a repository with git fetch

After you clone a repository and commit a few changes of your own, you may wish to check the original repository for updates.

The `git-fetch` command, with no arguments, will update all of the remote-tracking branches to the latest version found in the original repository. It will not touch any of your own branches—​not even the "master" branch that was created for you on clone.

## <span id="fetching-branches"></span>Fetching branches from other repositories

You can also track branches from repositories other than the one you cloned from, using <a href="git-remote.html" class="ulink">git-remote(1)</a>:

    $ git remote add staging git://git.kernel.org/.../gregkh/staging.git
    $ git fetch staging
    ...
    From git://git.kernel.org/pub/scm/linux/kernel/git/gregkh/staging
     * [new branch]      master     -> staging/master
     * [new branch]      staging-linus -> staging/staging-linus
     * [new branch]      staging-next -> staging/staging-next

New remote-tracking branches will be stored under the shorthand name that you gave `git remote add`, in this case `staging`:

    $ git branch -r
      origin/HEAD -> origin/master
      origin/master
      staging/master
      staging/staging-linus
      staging/staging-next

If you run `git fetch <remote>` later, the remote-tracking branches for the named `<remote>` will be updated.

If you examine the file `.git/config`, you will see that Git has added a new stanza:

    $ cat .git/config
    ...
    [remote "staging"]
            url = git://git.kernel.org/pub/scm/linux/kernel/git/gregkh/staging.git
            fetch = +refs/heads/*:refs/remotes/staging/*
    ...

This is what causes Git to track the remote’s branches; you may modify or delete these configuration options by editing `.git/config` with a text editor. (See the "CONFIGURATION FILE" section of <a href="git-config.html" class="ulink">git-config(1)</a> for details.)

**Table of Contents**

<span class="section">[How to use bisect to find a regression](#using-bisect)</span>

<span class="section">[Naming commits](#naming-commits)</span>

<span class="section">[Creating tags](#creating-tags)</span>

<span class="section">[Browsing revisions](#browsing-revisions)</span>

<span class="section">[Generating diffs](#generating-diffs)</span>

<span class="section">[Viewing old file versions](#viewing-old-file-versions)</span>

<span class="section">[Examples](#history-examples)</span>

<span class="section">[Counting the number of commits on a branch](#counting-commits-on-a-branch)</span>

<span class="section">[Check whether two branches point at the same history](#checking-for-equal-branches)</span>

<span class="section">[Find first tagged version including a given fix](#finding-tagged-descendants)</span>

<span class="section">[Showing commits unique to a given branch](#showing-commits-unique-to-a-branch)</span>

<span class="section">[Creating a changelog and tarball for a software release](#making-a-release)</span>

<span class="section">[Finding commits referencing a file with given content](#Finding-commits-With-given-Content)</span>

Git is best thought of as a tool for storing the history of a collection of files. It does this by storing compressed snapshots of the contents of a file hierarchy, together with "commits" which show the relationships between these snapshots.

Git provides extremely flexible and fast tools for exploring the history of a project.

We start with one specialized tool that is useful for finding the commit that introduced a bug into a project.

## <span id="using-bisect"></span>How to use bisect to find a regression

Suppose version 2.6.18 of your project worked, but the version at "master" crashes. Sometimes the best way to find the cause of such a regression is to perform a brute-force search through the project’s history to find the particular commit that caused the problem. The <a href="git-bisect.html" class="ulink">git-bisect(1)</a> command can help you do this:

    $ git bisect start
    $ git bisect good v2.6.18
    $ git bisect bad master
    Bisecting: 3537 revisions left to test after this
    [65934a9a028b88e83e2b0f8b36618fe503349f8e] BLOCK: Make USB storage depend on SCSI rather than selecting it [try #6]

If you run `git branch` at this point, you’ll see that Git has temporarily moved you in "(no branch)". HEAD is now detached from any branch and points directly to a commit (with commit id 65934) that is reachable from "master" but not from v2.6.18. Compile and test it, and see whether it crashes. Assume it does crash. Then:

    $ git bisect bad
    Bisecting: 1769 revisions left to test after this
    [7eff82c8b1511017ae605f0c99ac275a7e21b867] i2c-core: Drop useless bitmaskings

checks out an older version. Continue like this, telling Git at each stage whether the version it gives you is good or bad, and notice that the number of revisions left to test is cut approximately in half each time.

After about 13 tests (in this case), it will output the commit id of the guilty commit. You can then examine the commit with <a href="git-show.html" class="ulink">git-show(1)</a>, find out who wrote it, and mail them your bug report with the commit id. Finally, run

    $ git bisect reset

to return you to the branch you were on before.

Note that the version which `git bisect` checks out for you at each point is just a suggestion, and you’re free to try a different version if you think it would be a good idea. For example, occasionally you may land on a commit that broke something unrelated; run

    $ git bisect visualize

which will run gitk and label the commit it chose with a marker that says "bisect". Choose a safe-looking commit nearby, note its commit id, and check it out with:

    $ git reset --hard fb47ddb2db

then test, run `bisect good` or `bisect bad` as appropriate, and continue.

Instead of `git bisect visualize` and then `git reset --hard fb47ddb2db`, you might just want to tell Git that you want to skip the current commit:

    $ git bisect skip

In this case, though, Git may not eventually be able to tell the first bad one between some first skipped commits and a later bad commit.

There are also ways to automate the bisecting process if you have a test script that can tell a good from a bad commit. See <a href="git-bisect.html" class="ulink">git-bisect(1)</a> for more information about this and other `git bisect` features.

## <span id="naming-commits"></span>Naming commits

We have seen several ways of naming commits already:

- 40-hexdigit object name
- branch name: refers to the commit at the head of the given branch
- tag name: refers to the commit pointed to by the given tag (we’ve seen branches and tags are special cases of <a href="#how-git-stores-references" class="link" title="Naming branches, tags, and other references">references</a>).
- HEAD: refers to the head of the current branch

There are many more; see the "SPECIFYING REVISIONS" section of the <a href="gitrevisions.html" class="ulink">gitrevisions(7)</a> man page for the complete list of ways to name revisions. Some examples:

    $ git show fb47ddb2 # the first few characters of the object name
                        # are usually enough to specify it uniquely
    $ git show HEAD^    # the parent of the HEAD commit
    $ git show HEAD^^   # the grandparent
    $ git show HEAD~4   # the great-great-grandparent

Recall that merge commits may have more than one parent; by default, `^` and `~` follow the first parent listed in the commit, but you can also choose:

    $ git show HEAD^1   # show the first parent of HEAD
    $ git show HEAD^2   # show the second parent of HEAD

In addition to HEAD, there are several other special names for commits:

Merges (to be discussed later), as well as operations such as `git reset`, which change the currently checked-out commit, generally set ORIG_HEAD to the value HEAD had before the current operation.

The `git fetch` operation always stores the head of the last fetched branch in FETCH_HEAD. For example, if you run `git fetch` without specifying a local branch as the target of the operation

    $ git fetch git://example.com/proj.git theirbranch

the fetched commits will still be available from FETCH_HEAD.

When we discuss merges we’ll also see the special name MERGE_HEAD, which refers to the other branch that we’re merging in to the current branch.

The <a href="git-rev-parse.html" class="ulink">git-rev-parse(1)</a> command is a low-level command that is occasionally useful for translating some name for a commit to the object name for that commit:

    $ git rev-parse origin
    e05db0fd4f31dde7005f075a84f96b360d05984b

## <span id="creating-tags"></span>Creating tags

We can also create a tag to refer to a particular commit; after running

    $ git tag stable-1 1b2e1d63ff

You can use `stable-1` to refer to the commit 1b2e1d63ff.

This creates a "lightweight" tag. If you would also like to include a comment with the tag, and possibly sign it cryptographically, then you should create a tag object instead; see the <a href="git-tag.html" class="ulink">git-tag(1)</a> man page for details.

## <span id="browsing-revisions"></span>Browsing revisions

The <a href="git-log.html" class="ulink">git-log(1)</a> command can show lists of commits. On its own, it shows all commits reachable from the parent commit; but you can also make more specific requests:

    $ git log v2.5..        # commits since (not reachable from) v2.5
    $ git log test..master  # commits reachable from master but not test
    $ git log master..test  # ...reachable from test but not master
    $ git log master...test # ...reachable from either test or master,
                            #    but not both
    $ git log --since="2 weeks ago" # commits from the last 2 weeks
    $ git log Makefile      # commits which modify Makefile
    $ git log fs/           # ... which modify any file under fs/
    $ git log -S'foo()'     # commits which add or remove any file data
                            # matching the string 'foo()'

And of course you can combine all of these; the following finds commits since v2.5 which touch the `Makefile` or any file under `fs`:

    $ git log v2.5.. Makefile fs/

You can also ask git log to show patches:

    $ git log -p

See the `--pretty` option in the <a href="git-log.html" class="ulink">git-log(1)</a> man page for more display options.

Note that git log starts with the most recent commit and works backwards through the parents; however, since Git history can contain multiple independent lines of development, the particular order that commits are listed in may be somewhat arbitrary.

## <span id="generating-diffs"></span>Generating diffs

You can generate diffs between any two versions using <a href="git-diff.html" class="ulink">git-diff(1)</a>:

    $ git diff master..test

That will produce the diff between the tips of the two branches. If you’d prefer to find the diff from their common ancestor to test, you can use three dots instead of two:

    $ git diff master...test

Sometimes what you want instead is a set of patches; for this you can use <a href="git-format-patch.html" class="ulink">git-format-patch(1)</a>:

    $ git format-patch master..test

will generate a file with a patch for each commit reachable from test but not from master.

## <span id="viewing-old-file-versions"></span>Viewing old file versions

You can always view an old version of a file by just checking out the correct revision first. But sometimes it is more convenient to be able to view an old version of a single file without checking anything out; this command does that:

    $ git show v2.5:fs/locks.c

Before the colon may be anything that names a commit, and after it may be any path to a file tracked by Git.

## <span id="history-examples"></span>Examples

### <span id="counting-commits-on-a-branch"></span>Counting the number of commits on a branch

Suppose you want to know how many commits you’ve made on `mybranch` since it diverged from `origin`:

    $ git log --pretty=oneline origin..mybranch | wc -l

Alternatively, you may often see this sort of thing done with the lower-level command <a href="git-rev-list.html" class="ulink">git-rev-list(1)</a>, which just lists the SHA-1’s of all the given commits:

    $ git rev-list origin..mybranch | wc -l

### <span id="checking-for-equal-branches"></span>Check whether two branches point at the same history

Suppose you want to check whether two branches point at the same point in history.

    $ git diff origin..master

will tell you whether the contents of the project are the same at the two branches; in theory, however, it’s possible that the same project contents could have been arrived at by two different historical routes. You could compare the object names:

    $ git rev-list origin
    e05db0fd4f31dde7005f075a84f96b360d05984b
    $ git rev-list master
    e05db0fd4f31dde7005f075a84f96b360d05984b

Or you could recall that the `...` operator selects all commits reachable from either one reference or the other but not both; so

    $ git log origin...master

will return no commits when the two branches are equal.

### <span id="finding-tagged-descendants"></span>Find first tagged version including a given fix

Suppose you know that the commit e05db0fd fixed a certain problem. You’d like to find the earliest tagged release that contains that fix.

Of course, there may be more than one answer—​if the history branched after commit e05db0fd, then there could be multiple "earliest" tagged releases.

You could just visually inspect the commits since e05db0fd:

    $ gitk e05db0fd..

or you can use <a href="git-name-rev.html" class="ulink">git-name-rev(1)</a>, which will give the commit a name based on any tag it finds pointing to one of the commit’s descendants:

    $ git name-rev --tags e05db0fd
    e05db0fd tags/v1.5.0-rc1^0~23

The <a href="git-describe.html" class="ulink">git-describe(1)</a> command does the opposite, naming the revision using a tag on which the given commit is based:

    $ git describe e05db0fd
    v1.5.0-rc0-260-ge05db0f

but that may sometimes help you guess which tags might come after the given commit.

If you just want to verify whether a given tagged version contains a given commit, you could use <a href="git-merge-base.html" class="ulink">git-merge-base(1)</a>:

    $ git merge-base e05db0fd v1.5.0-rc1
    e05db0fd4f31dde7005f075a84f96b360d05984b

The merge-base command finds a common ancestor of the given commits, and always returns one or the other in the case where one is a descendant of the other; so the above output shows that e05db0fd actually is an ancestor of v1.5.0-rc1.

Alternatively, note that

    $ git log v1.5.0-rc1..e05db0fd

will produce empty output if and only if v1.5.0-rc1 includes e05db0fd, because it outputs only commits that are not reachable from v1.5.0-rc1.

As yet another alternative, the <a href="git-show-branch.html" class="ulink">git-show-branch(1)</a> command lists the commits reachable from its arguments with a display on the left-hand side that indicates which arguments that commit is reachable from. So, if you run something like

    $ git show-branch e05db0fd v1.5.0-rc0 v1.5.0-rc1 v1.5.0-rc2
    ! [e05db0fd] Fix warnings in sha1_file.c - use C99 printf format if
    available
     ! [v1.5.0-rc0] GIT v1.5.0 preview
      ! [v1.5.0-rc1] GIT v1.5.0-rc1
       ! [v1.5.0-rc2] GIT v1.5.0-rc2
    ...

then a line like

    + ++ [e05db0fd] Fix warnings in sha1_file.c - use C99 printf format if
    available

shows that e05db0fd is reachable from itself, from v1.5.0-rc1, and from v1.5.0-rc2, and not from v1.5.0-rc0.

### <span id="showing-commits-unique-to-a-branch"></span>Showing commits unique to a given branch

Suppose you would like to see all the commits reachable from the branch head named `master` but not from any other head in your repository.

We can list all the heads in this repository with <a href="git-show-ref.html" class="ulink">git-show-ref(1)</a>:

    $ git show-ref --heads
    bf62196b5e363d73353a9dcf094c59595f3153b7 refs/heads/core-tutorial
    db768d5504c1bb46f63ee9d6e1772bd047e05bf9 refs/heads/maint
    a07157ac624b2524a059a3414e99f6f44bebc1e7 refs/heads/master
    24dbc180ea14dc1aebe09f14c8ecf32010690627 refs/heads/tutorial-2
    1e87486ae06626c2f31eaa63d26fc0fd646c8af2 refs/heads/tutorial-fixes

We can get just the branch-head names, and remove `master`, with the help of the standard utilities cut and grep:

    $ git show-ref --heads | cut -d' ' -f2 | grep -v '^refs/heads/master'
    refs/heads/core-tutorial
    refs/heads/maint
    refs/heads/tutorial-2
    refs/heads/tutorial-fixes

And then we can ask to see all the commits reachable from master but not from these other heads:

    $ gitk master --not $( git show-ref --heads | cut -d' ' -f2 |
                                    grep -v '^refs/heads/master' )

Obviously, endless variations are possible; for example, to see all commits reachable from some head but not from any tag in the repository:

    $ gitk $( git show-ref --heads ) --not  $( git show-ref --tags )

(See <a href="gitrevisions.html" class="ulink">gitrevisions(7)</a> for explanations of commit-selecting syntax such as `--not`.)

### <span id="making-a-release"></span>Creating a changelog and tarball for a software release

The <a href="git-archive.html" class="ulink">git-archive(1)</a> command can create a tar or zip archive from any version of a project; for example:

    $ git archive -o latest.tar.gz --prefix=project/ HEAD

will use HEAD to produce a gzipped tar archive in which each filename is preceded by `project/`. The output file format is inferred from the output file extension if possible, see <a href="git-archive.html" class="ulink">git-archive(1)</a> for details.

Versions of Git older than 1.7.7 don’t know about the `tar.gz` format, you’ll need to use gzip explicitly:

    $ git archive --format=tar --prefix=project/ HEAD | gzip >latest.tar.gz

If you’re releasing a new version of a software project, you may want to simultaneously make a changelog to include in the release announcement.

Linus Torvalds, for example, makes new kernel releases by tagging them, then running:

    $ release-script 2.6.12 2.6.13-rc6 2.6.13-rc7

where release-script is a shell script that looks like:

    #!/bin/sh
    stable="$1"
    last="$2"
    new="$3"
    echo "# git tag v$new"
    echo "git archive --prefix=linux-$new/ v$new | gzip -9 > ../linux-$new.tar.gz"
    echo "git diff v$stable v$new | gzip -9 > ../patch-$new.gz"
    echo "git log --no-merges v$new ^v$last > ../ChangeLog-$new"
    echo "git shortlog --no-merges v$new ^v$last > ../ShortLog"
    echo "git diff --stat --summary -M v$last v$new > ../diffstat-$new"

and then he just cut-and-pastes the output commands after verifying that they look OK.

### <span id="Finding-commits-With-given-Content"></span>Finding commits referencing a file with given content

Somebody hands you a copy of a file, and asks which commits modified a file such that it contained the given content either before or after the commit. You can find out with this:

    $  git log --raw --abbrev=40 --pretty=oneline |
            grep -B 1 `git hash-object filename`

Figuring out why this works is left as an exercise to the (advanced) student. The <a href="git-log.html" class="ulink">git-log(1)</a>, <a href="git-diff-tree.html" class="ulink">git-diff-tree(1)</a>, and <a href="git-hash-object.html" class="ulink">git-hash-object(1)</a> man pages may prove helpful.

**Table of Contents**

<span class="section">[Telling Git your name](#telling-git-your-name)</span>

<span class="section">[Creating a new repository](#creating-a-new-repository)</span>

<span class="section">[How to make a commit](#how-to-make-a-commit)</span>

<span class="section">[Creating good commit messages](#creating-good-commit-messages)</span>

<span class="section">[Ignoring files](#ignoring-files)</span>

<span class="section">[How to merge](#how-to-merge)</span>

<span class="section">[Resolving a merge](#resolving-a-merge)</span>

<span class="section">[Getting conflict-resolution help during a merge](#conflict-resolution)</span>

<span class="section">[Undoing a merge](#undoing-a-merge)</span>

<span class="section">[Fast-forward merges](#fast-forwards)</span>

<span class="section">[Fixing mistakes](#fixing-mistakes)</span>

<span class="section">[Fixing a mistake with a new commit](#reverting-a-commit)</span>

<span class="section">[Fixing a mistake by rewriting history](#fixing-a-mistake-by-rewriting-history)</span>

<span class="section">[Checking out an old version of a file](#checkout-of-path)</span>

<span class="section">[Temporarily setting aside work in progress](#interrupted-work)</span>

<span class="section">[Ensuring good performance](#ensuring-good-performance)</span>

<span class="section">[Ensuring reliability](#ensuring-reliability)</span>

<span class="section">[Checking the repository for corruption](#checking-for-corruption)</span>

<span class="section">[Recovering lost changes](#recovering-lost-changes)</span>

## <span id="telling-git-your-name"></span>Telling Git your name

Before creating any commits, you should introduce yourself to Git. The easiest way to do so is to use <a href="git-config.html" class="ulink">git-config(1)</a>:

    $ git config --global user.name 'Your Name Comes Here'
    $ git config --global user.email 'you@yourdomain.example.com'

Which will add the following to a file named `.gitconfig` in your home directory:

    [user]
            name = Your Name Comes Here
            email = you@yourdomain.example.com

See the "CONFIGURATION FILE" section of <a href="git-config.html" class="ulink">git-config(1)</a> for details on the configuration file. The file is plain text, so you can also edit it with your favorite editor.

## <span id="creating-a-new-repository"></span>Creating a new repository

Creating a new repository from scratch is very easy:

    $ mkdir project
    $ cd project
    $ git init

If you have some initial content (say, a tarball):

    $ tar xzvf project.tar.gz
    $ cd project
    $ git init
    $ git add . # include everything below ./ in the first commit:
    $ git commit

## <span id="how-to-make-a-commit"></span>How to make a commit

Creating a new commit takes three steps:

1.  Making some changes to the working directory using your favorite editor.
2.  Telling Git about your changes.
3.  Creating the commit using the content you told Git about in step 2.

In practice, you can interleave and repeat steps 1 and 2 as many times as you want: in order to keep track of what you want committed at step 3, Git maintains a snapshot of the tree’s contents in a special staging area called "the index."

At the beginning, the content of the index will be identical to that of the HEAD. The command `git diff --cached`, which shows the difference between the HEAD and the index, should therefore produce no output at that point.

Modifying the index is easy:

To update the index with the contents of a new or modified file, use

    $ git add path/to/file

To remove a file from the index and from the working tree, use

    $ git rm path/to/file

After each step you can verify that

    $ git diff --cached

always shows the difference between the HEAD and the index file—​this is what you’d commit if you created the commit now—​and that

    $ git diff

shows the difference between the working tree and the index file.

Note that `git add` always adds just the current contents of a file to the index; further changes to the same file will be ignored unless you run `git add` on the file again.

When you’re ready, just run

    $ git commit

and Git will prompt you for a commit message and then create the new commit. Check to make sure it looks like what you expected with

    $ git show

As a special shortcut,

    $ git commit -a

will update the index with any files that you’ve modified or removed and create a commit, all in one step.

A number of commands are useful for keeping track of what you’re about to commit:

    $ git diff --cached # difference between HEAD and the index; what
                        # would be committed if you ran "commit" now.
    $ git diff          # difference between the index file and your
                        # working directory; changes that would not
                        # be included if you ran "commit" now.
    $ git diff HEAD     # difference between HEAD and working tree; what
                        # would be committed if you ran "commit -a" now.
    $ git status        # a brief per-file summary of the above.

You can also use <a href="git-gui.html" class="ulink">git-gui(1)</a> to create commits, view changes in the index and the working tree files, and individually select diff hunks for inclusion in the index (by right-clicking on the diff hunk and choosing "Stage Hunk For Commit").

## <span id="creating-good-commit-messages"></span>Creating good commit messages

Though not required, it’s a good idea to begin the commit message with a single short (less than 50 character) line summarizing the change, followed by a blank line and then a more thorough description. The text up to the first blank line in a commit message is treated as the commit title, and that title is used throughout Git. For example, <a href="git-format-patch.html" class="ulink">git-format-patch(1)</a> turns a commit into email, and it uses the title on the Subject line and the rest of the commit in the body.

## <span id="ignoring-files"></span>Ignoring files

A project will often generate files that you do <span class="emphasis">_not_</span> want to track with Git. This typically includes files generated by a build process or temporary backup files made by your editor. Of course, <span class="emphasis">_not_</span> tracking files with Git is just a matter of <span class="emphasis">_not_</span> calling `git add` on them. But it quickly becomes annoying to have these untracked files lying around; e.g. they make `git add .` practically useless, and they keep showing up in the output of `git status`.

You can tell Git to ignore certain files by creating a file called `.gitignore` in the top level of your working directory, with contents such as:

    # Lines starting with '#' are considered comments.
    # Ignore any file named foo.txt.
    foo.txt
    # Ignore (generated) html files,
    *.html
    # except foo.html which is maintained by hand.
    !foo.html
    # Ignore objects and archives.
    *.[oa]

See <a href="gitignore.html" class="ulink">gitignore(5)</a> for a detailed explanation of the syntax. You can also place .gitignore files in other directories in your working tree, and they will apply to those directories and their subdirectories. The `.gitignore` files can be added to your repository like any other files (just run `git add .gitignore` and `git commit`, as usual), which is convenient when the exclude patterns (such as patterns matching build output files) would also make sense for other users who clone your repository.

If you wish the exclude patterns to affect only certain repositories (instead of every repository for a given project), you may instead put them in a file in your repository named `.git/info/exclude`, or in any file specified by the `core.excludesFile` configuration variable. Some Git commands can also take exclude patterns directly on the command line. See <a href="gitignore.html" class="ulink">gitignore(5)</a> for the details.

## <span id="how-to-merge"></span>How to merge

You can rejoin two diverging branches of development using <a href="git-merge.html" class="ulink">git-merge(1)</a>:

    $ git merge branchname

merges the development in the branch `branchname` into the current branch.

A merge is made by combining the changes made in `branchname` and the changes made up to the latest commit in your current branch since their histories forked. The work tree is overwritten by the result of the merge when this combining is done cleanly, or overwritten by a half-merged results when this combining results in conflicts. Therefore, if you have uncommitted changes touching the same files as the ones impacted by the merge, Git will refuse to proceed. Most of the time, you will want to commit your changes before you can merge, and if you don’t, then <a href="git-stash.html" class="ulink">git-stash(1)</a> can take these changes away while you’re doing the merge, and reapply them afterwards.

If the changes are independent enough, Git will automatically complete the merge and commit the result (or reuse an existing commit in case of <a href="#fast-forwards" class="link" title="Fast-forward merges">fast-forward</a>, see below). On the other hand, if there are conflicts—​for example, if the same file is modified in two different ways in the remote branch and the local branch—​then you are warned; the output may look something like this:

    $ git merge next
     100% (4/4) done
    Auto-merged file.txt
    CONFLICT (content): Merge conflict in file.txt
    Automatic merge failed; fix conflicts and then commit the result.

Conflict markers are left in the problematic files, and after you resolve the conflicts manually, you can update the index with the contents and run Git commit, as you normally would when creating a new file.

If you examine the resulting commit using gitk, you will see that it has two parents, one pointing to the top of the current branch, and one to the top of the other branch.

## <span id="resolving-a-merge"></span>Resolving a merge

When a merge isn’t resolved automatically, Git leaves the index and the working tree in a special state that gives you all the information you need to help resolve the merge.

Files with conflicts are marked specially in the index, so until you resolve the problem and update the index, <a href="git-commit.html" class="ulink">git-commit(1)</a> will fail:

    $ git commit
    file.txt: needs merge

Also, <a href="git-status.html" class="ulink">git-status(1)</a> will list those files as "unmerged", and the files with conflicts will have conflict markers added, like this:

    <<<<<<< HEAD:file.txt
    Hello world
    =======
    Goodbye
    >>>>>>> 77976da35a11db4580b80ae27e8d65caf5208086:file.txt

All you need to do is edit the files to resolve the conflicts, and then

    $ git add file.txt
    $ git commit

Note that the commit message will already be filled in for you with some information about the merge. Normally you can just use this default message unchanged, but you may add additional commentary of your own if desired.

The above is all you need to know to resolve a simple merge. But Git also provides more information to help resolve conflicts:

### <span id="conflict-resolution"></span>Getting conflict-resolution help during a merge

All of the changes that Git was able to merge automatically are already added to the index file, so <a href="git-diff.html" class="ulink">git-diff(1)</a> shows only the conflicts. It uses an unusual syntax:

    $ git diff
    diff --cc file.txt
    index 802992c,2b60207..0000000
    --- a/file.txt
    +++ b/file.txt
    @@@ -1,1 -1,1 +1,5 @@@
    ++<<<<<<< HEAD:file.txt
     +Hello world
    ++=======
    + Goodbye
    ++>>>>>>> 77976da35a11db4580b80ae27e8d65caf5208086:file.txt

Recall that the commit which will be committed after we resolve this conflict will have two parents instead of the usual one: one parent will be HEAD, the tip of the current branch; the other will be the tip of the other branch, which is stored temporarily in MERGE_HEAD.

During the merge, the index holds three versions of each file. Each of these three "file stages" represents a different version of the file:

    $ git show :1:file.txt  # the file in a common ancestor of both branches
    $ git show :2:file.txt  # the version from HEAD.
    $ git show :3:file.txt  # the version from MERGE_HEAD.

When you ask <a href="git-diff.html" class="ulink">git-diff(1)</a> to show the conflicts, it runs a three-way diff between the conflicted merge results in the work tree with stages 2 and 3 to show only hunks whose contents come from both sides, mixed (in other words, when a hunk’s merge results come only from stage 2, that part is not conflicting and is not shown. Same for stage 3).

The diff above shows the differences between the working-tree version of file.txt and the stage 2 and stage 3 versions. So instead of preceding each line by a single `+` or `-`, it now uses two columns: the first column is used for differences between the first parent and the working directory copy, and the second for differences between the second parent and the working directory copy. (See the "COMBINED DIFF FORMAT" section of <a href="git-diff-files.html" class="ulink">git-diff-files(1)</a> for a details of the format.)

After resolving the conflict in the obvious way (but before updating the index), the diff will look like:

    $ git diff
    diff --cc file.txt
    index 802992c,2b60207..0000000
    --- a/file.txt
    +++ b/file.txt
    @@@ -1,1 -1,1 +1,1 @@@
    - Hello world
     -Goodbye
    ++Goodbye world

This shows that our resolved version deleted "Hello world" from the first parent, deleted "Goodbye" from the second parent, and added "Goodbye world", which was previously absent from both.

Some special diff options allow diffing the working directory against any of these stages:

    $ git diff -1 file.txt          # diff against stage 1
    $ git diff --base file.txt      # same as the above
    $ git diff -2 file.txt          # diff against stage 2
    $ git diff --ours file.txt      # same as the above
    $ git diff -3 file.txt          # diff against stage 3
    $ git diff --theirs file.txt    # same as the above.

The <a href="git-log.html" class="ulink">git-log(1)</a> and <a href="gitk.html" class="ulink">gitk(1)</a> commands also provide special help for merges:

    $ git log --merge
    $ gitk --merge

These will display all commits which exist only on HEAD or on MERGE_HEAD, and which touch an unmerged file.

You may also use <a href="git-mergetool.html" class="ulink">git-mergetool(1)</a>, which lets you merge the unmerged files using external tools such as Emacs or kdiff3.

Each time you resolve the conflicts in a file and update the index:

    $ git add file.txt

the different stages of that file will be "collapsed", after which `git diff` will (by default) no longer show diffs for that file.

## <span id="undoing-a-merge"></span>Undoing a merge

If you get stuck and decide to just give up and throw the whole mess away, you can always return to the pre-merge state with

    $ git merge --abort

Or, if you’ve already committed the merge that you want to throw away,

    $ git reset --hard ORIG_HEAD

However, this last command can be dangerous in some cases—​never throw away a commit you have already committed if that commit may itself have been merged into another branch, as doing so may confuse further merges.

## <span id="fast-forwards"></span>Fast-forward merges

There is one special case not mentioned above, which is treated differently. Normally, a merge results in a merge commit, with two parents, one pointing at each of the two lines of development that were merged.

However, if the current branch is an ancestor of the other—​so every commit present in the current branch is already contained in the other branch—​then Git just performs a "fast-forward"; the head of the current branch is moved forward to point at the head of the merged-in branch, without any new commits being created.

## <span id="fixing-mistakes"></span>Fixing mistakes

If you’ve messed up the working tree, but haven’t yet committed your mistake, you can return the entire working tree to the last committed state with

    $ git restore --staged --worktree :/

If you make a commit that you later wish you hadn’t, there are two fundamentally different ways to fix the problem:

1.  You can create a new commit that undoes whatever was done by the old commit. This is the correct thing if your mistake has already been made public.
2.  You can go back and modify the old commit. You should never do this if you have already made the history public; Git does not normally expect the "history" of a project to change, and cannot correctly perform repeated merges from a branch that has had its history changed.

### <span id="reverting-a-commit"></span>Fixing a mistake with a new commit

Creating a new commit that reverts an earlier change is very easy; just pass the <a href="git-revert.html" class="ulink">git-revert(1)</a> command a reference to the bad commit; for example, to revert the most recent commit:

    $ git revert HEAD

This will create a new commit which undoes the change in HEAD. You will be given a chance to edit the commit message for the new commit.

You can also revert an earlier change, for example, the next-to-last:

    $ git revert HEAD^

In this case Git will attempt to undo the old change while leaving intact any changes made since then. If more recent changes overlap with the changes to be reverted, then you will be asked to fix conflicts manually, just as in the case of <a href="#resolving-a-merge" class="link" title="Resolving a merge">resolving a merge</a>.

### <span id="fixing-a-mistake-by-rewriting-history"></span>Fixing a mistake by rewriting history

If the problematic commit is the most recent commit, and you have not yet made that commit public, then you may just <a href="#undoing-a-merge" class="link" title="Undoing a merge">destroy it using <code class="literal">git reset</code></a>.

Alternatively, you can edit the working directory and update the index to fix your mistake, just as if you were going to <a href="#how-to-make-a-commit" class="link" title="How to make a commit">create a new commit</a>, then run

    $ git commit --amend

which will replace the old commit by a new commit incorporating your changes, giving you a chance to edit the old commit message first.

Again, you should never do this to a commit that may already have been merged into another branch; use <a href="git-revert.html" class="ulink">git-revert(1)</a> instead in that case.

It is also possible to replace commits further back in the history, but this is an advanced topic to be left for <a href="#cleaning-up-history" class="link" title="Chapter 5. Rewriting history and maintaining patch series">another chapter</a>.

### <span id="checkout-of-path"></span>Checking out an old version of a file

In the process of undoing a previous bad change, you may find it useful to check out an older version of a particular file using <a href="git-restore.html" class="ulink">git-restore(1)</a>. The command

    $ git restore --source=HEAD^ path/to/file

replaces path/to/file by the contents it had in the commit HEAD^, and also updates the index to match. It does not change branches.

If you just want to look at an old version of the file, without modifying the working directory, you can do that with <a href="git-show.html" class="ulink">git-show(1)</a>:

    $ git show HEAD^:path/to/file

which will display the given version of the file.

### <span id="interrupted-work"></span>Temporarily setting aside work in progress

While you are in the middle of working on something complicated, you find an unrelated but obvious and trivial bug. You would like to fix it before continuing. You can use <a href="git-stash.html" class="ulink">git-stash(1)</a> to save the current state of your work, and after fixing the bug (or, optionally after doing so on a different branch and then coming back), unstash the work-in-progress changes.

    $ git stash push -m "work in progress for foo feature"

This command will save your changes away to the `stash`, and reset your working tree and the index to match the tip of your current branch. Then you can make your fix as usual.

    ... edit and test ...
    $ git commit -a -m "blorpl: typofix"

After that, you can go back to what you were working on with `git stash pop`:

    $ git stash pop

## <span id="ensuring-good-performance"></span>Ensuring good performance

On large repositories, Git depends on compression to keep the history information from taking up too much space on disk or in memory. Some Git commands may automatically run <a href="git-gc.html" class="ulink">git-gc(1)</a>, so you don’t have to worry about running it manually. However, compressing a large repository may take a while, so you may want to call `gc` explicitly to avoid automatic compression kicking in when it is not convenient.

## <span id="ensuring-reliability"></span>Ensuring reliability

### <span id="checking-for-corruption"></span>Checking the repository for corruption

The <a href="git-fsck.html" class="ulink">git-fsck(1)</a> command runs a number of self-consistency checks on the repository, and reports on any problems. This may take some time.

    $ git fsck
    dangling commit 7281251ddd2a61e38657c827739c57015671a6b3
    dangling commit 2706a059f258c6b245f298dc4ff2ccd30ec21a63
    dangling commit 13472b7c4b80851a1bc551779171dcb03655e9b5
    dangling blob 218761f9d90712d37a9c5e36f406f92202db07eb
    dangling commit bf093535a34a4d35731aa2bd90fe6b176302f14f
    dangling commit 8e4bec7f2ddaa268bef999853c25755452100f8e
    dangling tree d50bb86186bf27b681d25af89d3b5b68382e4085
    dangling tree b24c2473f1fd3d91352a624795be026d64c8841f
    ...

You will see informational messages on dangling objects. They are objects that still exist in the repository but are no longer referenced by any of your branches, and can (and will) be removed after a while with `gc`. You can run `git fsck --no-dangling` to suppress these messages, and still view real errors.

### <span id="recovering-lost-changes"></span>Recovering lost changes

#### <span id="reflogs"></span>Reflogs

Say you modify a branch with <a href="#fixing-mistakes" class="link" title="Fixing mistakes"><code class="literal">git reset --hard</code></a>, and then realize that the branch was the only reference you had to that point in history.

Fortunately, Git also keeps a log, called a "reflog", of all the previous values of each branch. So in this case you can still find the old history using, for example,

    $ git log master@{1}

This lists the commits reachable from the previous version of the `master` branch head. This syntax can be used with any Git command that accepts a commit, not just with `git log`. Some other examples:

    $ git show master@{2}           # See where the branch pointed 2,
    $ git show master@{3}           # 3, ... changes ago.
    $ gitk master@{yesterday}       # See where it pointed yesterday,
    $ gitk master@{"1 week ago"}    # ... or last week
    $ git log --walk-reflogs master # show reflog entries for master

A separate reflog is kept for the HEAD, so

    $ git show HEAD@{"1 week ago"}

will show what HEAD pointed to one week ago, not what the current branch pointed to one week ago. This allows you to see the history of what you’ve checked out.

The reflogs are kept by default for 30 days, after which they may be pruned. See <a href="git-reflog.html" class="ulink">git-reflog(1)</a> and <a href="git-gc.html" class="ulink">git-gc(1)</a> to learn how to control this pruning, and see the "SPECIFYING REVISIONS" section of <a href="gitrevisions.html" class="ulink">gitrevisions(7)</a> for details.

Note that the reflog history is very different from normal Git history. While normal history is shared by every repository that works on the same project, the reflog history is not shared: it tells you only about how the branches in your local repository have changed over time.

#### <span id="dangling-object-recovery"></span>Examining dangling objects

In some situations the reflog may not be able to save you. For example, suppose you delete a branch, then realize you need the history it contained. The reflog is also deleted; however, if you have not yet pruned the repository, then you may still be able to find the lost commits in the dangling objects that `git fsck` reports. See <a href="#dangling-objects" class="xref" title="Dangling objects">the section called “Dangling objects”</a> for the details.

    $ git fsck
    dangling commit 7281251ddd2a61e38657c827739c57015671a6b3
    dangling commit 2706a059f258c6b245f298dc4ff2ccd30ec21a63
    dangling commit 13472b7c4b80851a1bc551779171dcb03655e9b5
    ...

You can examine one of those dangling commits with, for example,

    $ gitk 7281251ddd --not --all

which does what it sounds like: it says that you want to see the commit history that is described by the dangling commit(s), but not the history that is described by all your existing branches and tags. Thus you get exactly the history reachable from that commit that is lost. (And notice that it might not be just one commit: we only report the "tip of the line" as being dangling, but there might be a whole deep and complex commit history that was dropped.)

If you decide you want the history back, you can always create a new reference pointing to it, for example, a new branch:

    $ git branch recovered-branch 7281251ddd

Other types of dangling objects (blobs and trees) are also possible, and dangling objects can arise in other situations.

**Table of Contents**

<span class="section">[Getting updates with git pull](#getting-updates-With-git-pull)</span>

<span class="section">[Submitting patches to a project](#submitting-patches)</span>

<span class="section">[Importing patches to a project](#importing-patches)</span>

<span class="section">[Public Git repositories](#public-repositories)</span>

<span class="section">[Setting up a public repository](#setting-up-a-public-repository)</span>

<span class="section">[Exporting a Git repository via the Git protocol](#exporting-via-git)</span>

<span class="section">[Exporting a git repository via HTTP](#exporting-via-http)</span>

<span class="section">[Pushing changes to a public repository](#pushing-changes-to-a-public-repository)</span>

<span class="section">[What to do when a push fails](#forcing-push)</span>

<span class="section">[Setting up a shared repository](#setting-up-a-shared-repository)</span>

<span class="section">[Allowing web browsing of a repository](#setting-up-gitweb)</span>

<span class="section">[How to get a Git repository with minimal history](#how-to-get-a-git-repository-with-minimal-history)</span>

<span class="section">[Examples](#sharing-development-examples)</span>

<span class="section">[Maintaining topic branches for a Linux subsystem maintainer](#maintaining-topic-branches)</span>

## <span id="getting-updates-With-git-pull"></span>Getting updates with git pull

After you clone a repository and commit a few changes of your own, you may wish to check the original repository for updates and merge them into your own work.

We have already seen <a href="#Updating-a-repository-With-git-fetch" class="link" title="Updating a repository with git fetch">how to keep remote-tracking branches up to date</a> with <a href="git-fetch.html" class="ulink">git-fetch(1)</a>, and how to merge two branches. So you can merge in changes from the original repository’s master branch with:

    $ git fetch
    $ git merge origin/master

However, the <a href="git-pull.html" class="ulink">git-pull(1)</a> command provides a way to do this in one step:

    $ git pull origin master

In fact, if you have `master` checked out, then this branch has been configured by `git clone` to get changes from the HEAD branch of the origin repository. So often you can accomplish the above with just a simple

    $ git pull

This command will fetch changes from the remote branches to your remote-tracking branches `origin/*`, and merge the default branch into the current branch.

More generally, a branch that is created from a remote-tracking branch will pull by default from that branch. See the descriptions of the `branch.<name>.remote` and `branch.<name>.merge` options in <a href="git-config.html" class="ulink">git-config(1)</a>, and the discussion of the `--track` option in <a href="git-checkout.html" class="ulink">git-checkout(1)</a>, to learn how to control these defaults.

In addition to saving you keystrokes, `git pull` also helps you by producing a default commit message documenting the branch and repository that you pulled from.

(But note that no such commit will be created in the case of a <a href="#fast-forwards" class="link" title="Fast-forward merges">fast-forward</a>; instead, your branch will just be updated to point to the latest commit from the upstream branch.)

The `git pull` command can also be given `.` as the "remote" repository, in which case it just merges in a branch from the current repository; so the commands

    $ git pull . branch
    $ git merge branch

are roughly equivalent.

## <span id="submitting-patches"></span>Submitting patches to a project

If you just have a few changes, the simplest way to submit them may just be to send them as patches in email:

First, use <a href="git-format-patch.html" class="ulink">git-format-patch(1)</a>; for example:

    $ git format-patch origin

will produce a numbered series of files in the current directory, one for each patch in the current branch but not in `origin/HEAD`.

`git format-patch` can include an initial "cover letter". You can insert commentary on individual patches after the three dash line which `format-patch` places after the commit message but before the patch itself. If you use `git notes` to track your cover letter material, `git format-patch --notes` will include the commit’s notes in a similar manner.

You can then import these into your mail client and send them by hand. However, if you have a lot to send at once, you may prefer to use the <a href="git-send-email.html" class="ulink">git-send-email(1)</a> script to automate the process. Consult the mailing list for your project first to determine their requirements for submitting patches.

## <span id="importing-patches"></span>Importing patches to a project

Git also provides a tool called <a href="git-am.html" class="ulink">git-am(1)</a> (am stands for "apply mailbox"), for importing such an emailed series of patches. Just save all of the patch-containing messages, in order, into a single mailbox file, say `patches.mbox`, then run

    $ git am -3 patches.mbox

Git will apply each patch in order; if any conflicts are found, it will stop, and you can fix the conflicts as described in "<a href="#resolving-a-merge" class="link" title="Resolving a merge">Resolving a merge</a>". (The `-3` option tells Git to perform a merge; if you would prefer it just to abort and leave your tree and index untouched, you may omit that option.)

Once the index is updated with the results of the conflict resolution, instead of creating a new commit, just run

    $ git am --continue

and Git will create the commit for you and continue applying the remaining patches from the mailbox.

The final result will be a series of commits, one for each patch in the original mailbox, with authorship and commit log message each taken from the message containing each patch.

## <span id="public-repositories"></span>Public Git repositories

Another way to submit changes to a project is to tell the maintainer of that project to pull the changes from your repository using <a href="git-pull.html" class="ulink">git-pull(1)</a>. In the section "<a href="#getting-updates-With-git-pull" class="link" title="Getting updates with git pull">Getting updates with <code class="literal">git pull</code></a>" we described this as a way to get updates from the "main" repository, but it works just as well in the other direction.

If you and the maintainer both have accounts on the same machine, then you can just pull changes from each other’s repositories directly; commands that accept repository URLs as arguments will also accept a local directory name:

    $ git clone /path/to/repository
    $ git pull /path/to/other/repository

or an ssh URL:

    $ git clone ssh://yourhost/~you/repository

For projects with few developers, or for synchronizing a few private repositories, this may be all you need.

However, the more common way to do this is to maintain a separate public repository (usually on a different host) for others to pull changes from. This is usually more convenient, and allows you to cleanly separate private work in progress from publicly visible work.

You will continue to do your day-to-day work in your personal repository, but periodically "push" changes from your personal repository into your public repository, allowing other developers to pull from that repository. So the flow of changes, in a situation where there is one other developer with a public repository, looks like this:

                          you push
    your personal repo ------------------> your public repo
          ^                                     |
          |                                     |
          | you pull                            | they pull
          |                                     |
          |                                     |
          |               they push             V
    their public repo <------------------- their repo

We explain how to do this in the following sections.

### <span id="setting-up-a-public-repository"></span>Setting up a public repository

Assume your personal repository is in the directory `~/proj`. We first create a new clone of the repository and tell `git daemon` that it is meant to be public:

    $ git clone --bare ~/proj proj.git
    $ touch proj.git/git-daemon-export-ok

The resulting directory proj.git contains a "bare" git repository—​it is just the contents of the `.git` directory, without any files checked out around it.

Next, copy `proj.git` to the server where you plan to host the public repository. You can use scp, rsync, or whatever is most convenient.

### <span id="exporting-via-git"></span>Exporting a Git repository via the Git protocol

This is the preferred method.

If someone else administers the server, they should tell you what directory to put the repository in, and what `git://` URL it will appear at. You can then skip to the section "<a href="#pushing-changes-to-a-public-repository" class="link" title="Pushing changes to a public repository">Pushing changes to a public repository</a>", below.

Otherwise, all you need to do is start <a href="git-daemon.html" class="ulink">git-daemon(1)</a>; it will listen on port 9418. By default, it will allow access to any directory that looks like a Git directory and contains the magic file git-daemon-export-ok. Passing some directory paths as `git daemon` arguments will further restrict the exports to those paths.

You can also run `git daemon` as an inetd service; see the <a href="git-daemon.html" class="ulink">git-daemon(1)</a> man page for details. (See especially the examples section.)

### <span id="exporting-via-http"></span>Exporting a git repository via HTTP

The Git protocol gives better performance and reliability, but on a host with a web server set up, HTTP exports may be simpler to set up.

All you need to do is place the newly created bare Git repository in a directory that is exported by the web server, and make some adjustments to give web clients some extra information they need:

    $ mv proj.git /home/you/public_html/proj.git
    $ cd proj.git
    $ git --bare update-server-info
    $ mv hooks/post-update.sample hooks/post-update

(For an explanation of the last two lines, see <a href="git-update-server-info.html" class="ulink">git-update-server-info(1)</a> and <a href="githooks.html" class="ulink">githooks(5)</a>.)

Advertise the URL of `proj.git`. Anybody else should then be able to clone or pull from that URL, for example with a command line like:

    $ git clone http://yourserver.com/~you/proj.git

(See also <a href="howto/setup-git-server-over-http.html" class="ulink">setup-git-server-over-http</a> for a slightly more sophisticated setup using WebDAV which also allows pushing over HTTP.)

### <span id="pushing-changes-to-a-public-repository"></span>Pushing changes to a public repository

Note that the two techniques outlined above (exporting via <a href="#exporting-via-http" class="link" title="Exporting a git repository via HTTP">http</a> or <a href="#exporting-via-git" class="link" title="Exporting a Git repository via the Git protocol">git</a>) allow other maintainers to fetch your latest changes, but they do not allow write access, which you will need to update the public repository with the latest changes created in your private repository.

The simplest way to do this is using <a href="git-push.html" class="ulink">git-push(1)</a> and ssh; to update the remote branch named `master` with the latest state of your branch named `master`, run

    $ git push ssh://yourserver.com/~you/proj.git master:master

or just

    $ git push ssh://yourserver.com/~you/proj.git master

As with `git fetch`, `git push` will complain if this does not result in a <a href="#fast-forwards" class="link" title="Fast-forward merges">fast-forward</a>; see the following section for details on handling this case.

Note that the target of a `push` is normally a <a href="#def_bare_repository" class="link">bare</a> repository. You can also push to a repository that has a checked-out working tree, but a push to update the currently checked-out branch is denied by default to prevent confusion. See the description of the receive.denyCurrentBranch option in <a href="git-config.html" class="ulink">git-config(1)</a> for details.

As with `git fetch`, you may also set up configuration options to save typing; so, for example:

    $ git remote add public-repo ssh://yourserver.com/~you/proj.git

adds the following to `.git/config`:

    [remote "public-repo"]
            url = yourserver.com:proj.git
            fetch = +refs/heads/*:refs/remotes/example/*

which lets you do the same push with just

    $ git push public-repo master

See the explanations of the `remote.<name>.url`, `branch.<name>.remote`, and `remote.<name>.push` options in <a href="git-config.html" class="ulink">git-config(1)</a> for details.

### <span id="forcing-push"></span>What to do when a push fails

If a push would not result in a <a href="#fast-forwards" class="link" title="Fast-forward merges">fast-forward</a> of the remote branch, then it will fail with an error like:

     ! [rejected]        master -> master (non-fast-forward)
    error: failed to push some refs to '...'
    hint: Updates were rejected because the tip of your current branch is behind
    hint: its remote counterpart. Integrate the remote changes (e.g.
    hint: 'git pull ...') before pushing again.
    hint: See the 'Note about fast-forwards' in 'git push --help' for details.

This can happen, for example, if you:

- use `git reset --hard` to remove already-published commits, or
- use `git commit --amend` to replace already-published commits (as in <a href="#fixing-a-mistake-by-rewriting-history" class="xref" title="Fixing a mistake by rewriting history">the section called “Fixing a mistake by rewriting history”</a>), or
- use `git rebase` to rebase any already-published commits (as in <a href="#using-git-rebase" class="xref" title="Keeping a patch series up to date using git rebase">the section called “Keeping a patch series up to date using git rebase”</a>).

You may force `git push` to perform the update anyway by preceding the branch name with a plus sign:

    $ git push ssh://yourserver.com/~you/proj.git +master

Note the addition of the `+` sign. Alternatively, you can use the `-f` flag to force the remote update, as in:

    $ git push -f ssh://yourserver.com/~you/proj.git master

Normally whenever a branch head in a public repository is modified, it is modified to point to a descendant of the commit that it pointed to before. By forcing a push in this situation, you break that convention. (See <a href="#problems-With-rewriting-history" class="xref" title="Problems with rewriting history">the section called “Problems with rewriting history”</a>.)

Nevertheless, this is a common practice for people that need a simple way to publish a work-in-progress patch series, and it is an acceptable compromise as long as you warn other developers that this is how you intend to manage the branch.

It’s also possible for a push to fail in this way when other people have the right to push to the same repository. In that case, the correct solution is to retry the push after first updating your work: either by a pull, or by a fetch followed by a rebase; see the <a href="#setting-up-a-shared-repository" class="link" title="Setting up a shared repository">next section</a> and <a href="gitcvs-migration.html" class="ulink">gitcvs-migration(7)</a> for more.

### <span id="setting-up-a-shared-repository"></span>Setting up a shared repository

Another way to collaborate is by using a model similar to that commonly used in CVS, where several developers with special rights all push to and pull from a single shared repository. See <a href="gitcvs-migration.html" class="ulink">gitcvs-migration(7)</a> for instructions on how to set this up.

However, while there is nothing wrong with Git’s support for shared repositories, this mode of operation is not generally recommended, simply because the mode of collaboration that Git supports—​by exchanging patches and pulling from public repositories—​has so many advantages over the central shared repository:

- Git’s ability to quickly import and merge patches allows a single maintainer to process incoming changes even at very high rates. And when that becomes too much, `git pull` provides an easy way for that maintainer to delegate this job to other maintainers while still allowing optional review of incoming changes.
- Since every developer’s repository has the same complete copy of the project history, no repository is special, and it is trivial for another developer to take over maintenance of a project, either by mutual agreement, or because a maintainer becomes unresponsive or difficult to work with.
- The lack of a central group of "committers" means there is less need for formal decisions about who is "in" and who is "out".

### <span id="setting-up-gitweb"></span>Allowing web browsing of a repository

The gitweb cgi script provides users an easy way to browse your project’s revisions, file contents and logs without having to install Git. Features like RSS/Atom feeds and blame/annotation details may optionally be enabled.

The <a href="git-instaweb.html" class="ulink">git-instaweb(1)</a> command provides a simple way to start browsing the repository using gitweb. The default server when using instaweb is lighttpd.

See the file gitweb/INSTALL in the Git source tree and <a href="gitweb.html" class="ulink">gitweb(1)</a> for instructions on details setting up a permanent installation with a CGI or Perl capable server.

## <span id="how-to-get-a-git-repository-with-minimal-history"></span>How to get a Git repository with minimal history

A <a href="#def_shallow_clone" class="link">shallow clone</a>, with its truncated history, is useful when one is interested only in recent history of a project and getting full history from the upstream is expensive.

A <a href="#def_shallow_clone" class="link">shallow clone</a> is created by specifying the <a href="git-clone.html" class="ulink">git-clone(1)</a> `--depth` switch. The depth can later be changed with the <a href="git-fetch.html" class="ulink">git-fetch(1)</a> `--depth` switch, or full history restored with `--unshallow`.

Merging inside a <a href="#def_shallow_clone" class="link">shallow clone</a> will work as long as a merge base is in the recent history. Otherwise, it will be like merging unrelated histories and may have to result in huge conflicts. This limitation may make such a repository unsuitable to be used in merge based workflows.

## <span id="sharing-development-examples"></span>Examples

### <span id="maintaining-topic-branches"></span>Maintaining topic branches for a Linux subsystem maintainer

This describes how Tony Luck uses Git in his role as maintainer of the IA64 architecture for the Linux kernel.

He uses two public branches:

- A "test" tree into which patches are initially placed so that they can get some exposure when integrated with other ongoing development. This tree is available to Andrew for pulling into -mm whenever he wants.
- A "release" tree into which tested patches are moved for final sanity checking, and as a vehicle to send them upstream to Linus (by sending him a "please pull" request.)

He also uses a set of temporary branches ("topic branches"), each containing a logical grouping of patches.

To set this up, first create your work tree by cloning Linus’s public tree:

    $ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git work
    $ cd work

Linus’s tree will be stored in the remote-tracking branch named origin/master, and can be updated using <a href="git-fetch.html" class="ulink">git-fetch(1)</a>; you can track other public trees using <a href="git-remote.html" class="ulink">git-remote(1)</a> to set up a "remote" and <a href="git-fetch.html" class="ulink">git-fetch(1)</a> to keep them up to date; see <a href="#repositories-and-branches" class="xref" title="Chapter 1. Repositories and Branches">Chapter 1, <em>Repositories and Branches</em></a>.

Now create the branches in which you are going to work; these start out at the current tip of origin/master branch, and should be set up (using the `--track` option to <a href="git-branch.html" class="ulink">git-branch(1)</a>) to merge changes in from Linus by default.

    $ git branch --track test origin/master
    $ git branch --track release origin/master

These can be easily kept up to date using <a href="git-pull.html" class="ulink">git-pull(1)</a>.

    $ git switch test && git pull
    $ git switch release && git pull

Important note! If you have any local changes in these branches, then this merge will create a commit object in the history (with no local changes Git will simply do a "fast-forward" merge). Many people dislike the "noise" that this creates in the Linux history, so you should avoid doing this capriciously in the `release` branch, as these noisy commits will become part of the permanent history when you ask Linus to pull from the release branch.

A few configuration variables (see <a href="git-config.html" class="ulink">git-config(1)</a>) can make it easy to push both branches to your public tree. (See <a href="#setting-up-a-public-repository" class="xref" title="Setting up a public repository">the section called “Setting up a public repository”</a>.)

    $ cat >> .git/config <<EOF
    [remote "mytree"]
            url =  master.kernel.org:/pub/scm/linux/kernel/git/aegl/linux.git
            push = release
            push = test
    EOF

Then you can push both the test and release trees using <a href="git-push.html" class="ulink">git-push(1)</a>:

    $ git push mytree

or push just one of the test and release branches using:

    $ git push mytree test

or

    $ git push mytree release

Now to apply some patches from the community. Think of a short snappy name for a branch to hold this patch (or related group of patches), and create a new branch from a recent stable tag of Linus’s branch. Picking a stable base for your branch will: 1) help you: by avoiding inclusion of unrelated and perhaps lightly tested changes 2) help future bug hunters that use `git bisect` to find problems

    $ git switch -c speed-up-spinlocks v2.6.35

Now you apply the patch(es), run some tests, and commit the change(s). If the patch is a multi-part series, then you should apply each as a separate commit to this branch.

    $ ... patch ... test  ... commit [ ... patch ... test ... commit ]*

When you are happy with the state of this change, you can merge it into the "test" branch in preparation to make it public:

    $ git switch test && git merge speed-up-spinlocks

It is unlikely that you would have any conflicts here …​ but you might if you spent a while on this step and had also pulled new versions from upstream.

Sometime later when enough time has passed and testing done, you can pull the same branch into the `release` tree ready to go upstream. This is where you see the value of keeping each patch (or patch series) in its own branch. It means that the patches can be moved into the `release` tree in any order.

    $ git switch release && git merge speed-up-spinlocks

After a while, you will have a number of branches, and despite the well chosen names you picked for each of them, you may forget what they are for, or what status they are in. To get a reminder of what changes are in a specific branch, use:

    $ git log linux..branchname | git shortlog

To see whether it has already been merged into the test or release branches, use:

    $ git log test..branchname

or

    $ git log release..branchname

(If this branch has not yet been merged, you will see some log entries. If it has been merged, then there will be no output.)

Once a patch completes the great cycle (moving from test to release, then pulled by Linus, and finally coming back into your local `origin/master` branch), the branch for this change is no longer needed. You detect this when the output from:

    $ git log origin..branchname

is empty. At this point the branch can be deleted:

    $ git branch -d branchname

Some changes are so trivial that it is not necessary to create a separate branch and then merge into each of the test and release branches. For these changes, just apply directly to the `release` branch, and then merge that into the `test` branch.

After pushing your work to `mytree`, you can use <a href="git-request-pull.html" class="ulink">git-request-pull(1)</a> to prepare a "please pull" request message to send to Linus:

    $ git push mytree
    $ git request-pull origin mytree release

Here are some of the scripts that simplify all this even further.

    ==== update script ====
    # Update a branch in my Git tree.  If the branch to be updated
    # is origin, then pull from kernel.org.  Otherwise merge
    # origin/master branch into test|release branch

    case "$1" in
    test|release)
            git checkout $1 && git pull . origin
            ;;
    origin)
            before=$(git rev-parse refs/remotes/origin/master)
            git fetch origin
            after=$(git rev-parse refs/remotes/origin/master)
            if [ $before != $after ]
            then
                    git log $before..$after | git shortlog
            fi
            ;;
    *)
            echo "usage: $0 origin|test|release" 1>&2
            exit 1
            ;;
    esac

    ==== merge script ====
    # Merge a branch into either the test or release branch

    pname=$0

    usage()
    {
            echo "usage: $pname branch test|release" 1>&2
            exit 1
    }

    git show-ref -q --verify -- refs/heads/"$1" || {
            echo "Can't see branch <$1>" 1>&2
            usage
    }

    case "$2" in
    test|release)
            if [ $(git log $2..$1 | wc -c) -eq 0 ]
            then
                    echo $1 already merged into $2 1>&2
                    exit 1
            fi
            git checkout $2 && git pull . $1
            ;;
    *)
            usage
            ;;
    esac

    ==== status script ====
    # report on status of my ia64 Git tree

    gb=$(tput setab 2)
    rb=$(tput setab 1)
    restore=$(tput setab 9)

    if [ `git rev-list test..release | wc -c` -gt 0 ]
    then
            echo $rb Warning: commits in release that are not in test $restore
            git log test..release
    fi

    for branch in `git show-ref --heads | sed 's|^.*/||'`
    do
            if [ $branch = test -o $branch = release ]
            then
                    continue
            fi

            echo -n $gb ======= $branch ====== $restore " "
            status=
            for ref in test release origin/master
            do
                    if [ `git rev-list $ref..$branch | wc -c` -gt 0 ]
                    then
                            status=$status${ref:0:1}
                    fi
            done
            case $status in
            trl)
                    echo $rb Need to pull into test $restore
                    ;;
            rl)
                    echo "In test"
                    ;;
            l)
                    echo "Waiting for linus"
                    ;;
            "")
                    echo $rb All done $restore
                    ;;
            *)
                    echo $rb "<$status>" $restore
                    ;;
            esac
            git log origin/master..$branch | git shortlog
    done

**Table of Contents**

<span class="section">[Creating the perfect patch series](#patch-series)</span>

<span class="section">[Keeping a patch series up to date using git rebase](#using-git-rebase)</span>

<span class="section">[Rewriting a single commit](#rewriting-one-commit)</span>

<span class="section">[Reordering or selecting from a patch series](#reordering-patch-series)</span>

<span class="section">[Using interactive rebases](#interactive-rebase)</span>

<span class="section">[Other tools](#patch-series-tools)</span>

<span class="section">[Problems with rewriting history](#problems-With-rewriting-history)</span>

<span class="section">[Why bisecting merge commits can be harder than bisecting linear history](#bisect-merges)</span>

Normally commits are only added to a project, never taken away or replaced. Git is designed with this assumption, and violating it will cause Git’s merge machinery (for example) to do the wrong thing.

However, there is a situation in which it can be useful to violate this assumption.

## <span id="patch-series"></span>Creating the perfect patch series

Suppose you are a contributor to a large project, and you want to add a complicated feature, and to present it to the other developers in a way that makes it easy for them to read your changes, verify that they are correct, and understand why you made each change.

If you present all of your changes as a single patch (or commit), they may find that it is too much to digest all at once.

If you present them with the entire history of your work, complete with mistakes, corrections, and dead ends, they may be overwhelmed.

So the ideal is usually to produce a series of patches such that:

1.  Each patch can be applied in order.
2.  Each patch includes a single logical change, together with a message explaining the change.
3.  No patch introduces a regression: after applying any initial part of the series, the resulting project still compiles and works, and has no bugs that it didn’t have before.
4.  The complete series produces the same end result as your own (probably much messier!) development process did.

We will introduce some tools that can help you do this, explain how to use them, and then explain some of the problems that can arise because you are rewriting history.

## <span id="using-git-rebase"></span>Keeping a patch series up to date using git rebase

Suppose that you create a branch `mywork` on a remote-tracking branch `origin`, and create some commits on top of it:

    $ git switch -c mywork origin
    $ vi file.txt
    $ git commit
    $ vi otherfile.txt
    $ git commit
    ...

You have performed no merges into mywork, so it is just a simple linear sequence of patches on top of `origin`:

     o--o--O <-- origin
            \
             a--b--c <-- mywork

Some more interesting work has been done in the upstream project, and `origin` has advanced:

     o--o--O--o--o--o <-- origin
            \
             a--b--c <-- mywork

At this point, you could use `pull` to merge your changes back in; the result would create a new merge commit, like this:

     o--o--O--o--o--o <-- origin
            \        \
             a--b--c--m <-- mywork

However, if you prefer to keep the history in mywork a simple series of commits without any merges, you may instead choose to use <a href="git-rebase.html" class="ulink">git-rebase(1)</a>:

    $ git switch mywork
    $ git rebase origin

This will remove each of your commits from mywork, temporarily saving them as patches (in a directory named `.git/rebase-apply`), update mywork to point at the latest version of origin, then apply each of the saved patches to the new mywork. The result will look like:

     o--o--O--o--o--o <-- origin
                     \
                      a'--b'--c' <-- mywork

In the process, it may discover conflicts. In that case it will stop and allow you to fix the conflicts; after fixing conflicts, use `git add` to update the index with those contents, and then, instead of running `git commit`, just run

    $ git rebase --continue

and Git will continue applying the rest of the patches.

At any point you may use the `--abort` option to abort this process and return mywork to the state it had before you started the rebase:

    $ git rebase --abort

If you need to reorder or edit a number of commits in a branch, it may be easier to use `git rebase -i`, which allows you to reorder and squash commits, as well as marking them for individual editing during the rebase. See <a href="#interactive-rebase" class="xref" title="Using interactive rebases">the section called “Using interactive rebases”</a> for details, and <a href="#reordering-patch-series" class="xref" title="Reordering or selecting from a patch series">the section called “Reordering or selecting from a patch series”</a> for alternatives.

## <span id="rewriting-one-commit"></span>Rewriting a single commit

We saw in <a href="#fixing-a-mistake-by-rewriting-history" class="xref" title="Fixing a mistake by rewriting history">the section called “Fixing a mistake by rewriting history”</a> that you can replace the most recent commit using

    $ git commit --amend

which will replace the old commit by a new commit incorporating your changes, giving you a chance to edit the old commit message first. This is useful for fixing typos in your last commit, or for adjusting the patch contents of a poorly staged commit.

If you need to amend commits from deeper in your history, you can use <a href="#interactive-rebase" class="link" title="Using interactive rebases">interactive rebase’s <code class="literal">edit</code> instruction</a>.

## <span id="reordering-patch-series"></span>Reordering or selecting from a patch series

Sometimes you want to edit a commit deeper in your history. One approach is to use `git format-patch` to create a series of patches and then reset the state to before the patches:

    $ git format-patch origin
    $ git reset --hard origin

Then modify, reorder, or eliminate patches as needed before applying them again with <a href="git-am.html" class="ulink">git-am(1)</a>:

    $ git am *.patch

## <span id="interactive-rebase"></span>Using interactive rebases

You can also edit a patch series with an interactive rebase. This is the same as <a href="#reordering-patch-series" class="link" title="Reordering or selecting from a patch series">reordering a patch series using <code class="literal">format-patch</code></a>, so use whichever interface you like best.

Rebase your current HEAD on the last commit you want to retain as-is. For example, if you want to reorder the last 5 commits, use:

    $ git rebase -i HEAD~5

This will open your editor with a list of steps to be taken to perform your rebase.

    pick deadbee The oneline of this commit
    pick fa1afe1 The oneline of the next commit
    ...

    # Rebase c0ffeee..deadbee onto c0ffeee
    #
    # Commands:
    #  p, pick = use commit
    #  r, reword = use commit, but edit the commit message
    #  e, edit = use commit, but stop for amending
    #  s, squash = use commit, but meld into previous commit
    #  f, fixup = like "squash", but discard this commit's log message
    #  x, exec = run command (the rest of the line) using shell
    #
    # These lines can be re-ordered; they are executed from top to bottom.
    #
    # If you remove a line here THAT COMMIT WILL BE LOST.
    #
    # However, if you remove everything, the rebase will be aborted.
    #
    # Note that empty commits are commented out

As explained in the comments, you can reorder commits, squash them together, edit commit messages, etc. by editing the list. Once you are satisfied, save the list and close your editor, and the rebase will begin.

The rebase will stop where `pick` has been replaced with `edit` or when a step in the list fails to mechanically resolve conflicts and needs your help. When you are done editing and/or resolving conflicts you can continue with `git rebase --continue`. If you decide that things are getting too hairy, you can always bail out with `git rebase --abort`. Even after the rebase is complete, you can still recover the original branch by using the <a href="#reflogs" class="link" title="Reflogs">reflog</a>.

For a more detailed discussion of the procedure and additional tips, see the "INTERACTIVE MODE" section of <a href="git-rebase.html" class="ulink">git-rebase(1)</a>.

## <span id="patch-series-tools"></span>Other tools

There are numerous other tools, such as StGit, which exist for the purpose of maintaining a patch series. These are outside of the scope of this manual.

## <span id="problems-With-rewriting-history"></span>Problems with rewriting history

The primary problem with rewriting the history of a branch has to do with merging. Suppose somebody fetches your branch and merges it into their branch, with a result something like this:

     o--o--O--o--o--o <-- origin
            \        \
             t--t--t--m <-- their branch:

Then suppose you modify the last three commits:

             o--o--o <-- new head of origin
            /
     o--o--O--o--o--o <-- old head of origin

If we examined all this history together in one repository, it will look like:

             o--o--o <-- new head of origin
            /
     o--o--O--o--o--o <-- old head of origin
            \        \
             t--t--t--m <-- their branch:

Git has no way of knowing that the new head is an updated version of the old head; it treats this situation exactly the same as it would if two developers had independently done the work on the old and new heads in parallel. At this point, if someone attempts to merge the new head in to their branch, Git will attempt to merge together the two (old and new) lines of development, instead of trying to replace the old by the new. The results are likely to be unexpected.

You may still choose to publish branches whose history is rewritten, and it may be useful for others to be able to fetch those branches in order to examine or test them, but they should not attempt to pull such branches into their own work.

For true distributed development that supports proper merging, published branches should never be rewritten.

## <span id="bisect-merges"></span>Why bisecting merge commits can be harder than bisecting linear history

The <a href="git-bisect.html" class="ulink">git-bisect(1)</a> command correctly handles history that includes merge commits. However, when the commit that it finds is a merge commit, the user may need to work harder than usual to figure out why that commit introduced a problem.

Imagine this history:

          ---Z---o---X---...---o---A---C---D
              \                       /
               o---o---Y---...---o---B

Suppose that on the upper line of development, the meaning of one of the functions that exists at Z is changed at commit X. The commits from Z leading to A change both the function’s implementation and all calling sites that exist at Z, as well as new calling sites they add, to be consistent. There is no bug at A.

Suppose that in the meantime on the lower line of development somebody adds a new calling site for that function at commit Y. The commits from Z leading to B all assume the old semantics of that function and the callers and the callee are consistent with each other. There is no bug at B, either.

Suppose further that the two development lines merge cleanly at C, so no conflict resolution is required.

Nevertheless, the code at C is broken, because the callers added on the lower line of development have not been converted to the new semantics introduced on the upper line of development. So if all you know is that D is bad, that Z is good, and that <a href="git-bisect.html" class="ulink">git-bisect(1)</a> identifies C as the culprit, how will you figure out that the problem is due to this change in semantics?

When the result of a `git bisect` is a non-merge commit, you should normally be able to discover the problem by examining just that commit. Developers can make this easy by breaking their changes into small self-contained commits. That won’t help in the case above, however, because the problem isn’t obvious from examination of any single commit; instead, a global view of the development is required. To make matters worse, the change in semantics in the problematic function may be just one small part of the changes in the upper line of development.

On the other hand, if instead of merging at C you had rebased the history between Z to B on top of A, you would have gotten this linear history:

        ---Z---o---X--...---o---A---o---o---Y*--...---o---B*--D*

Bisecting between Z and D\* would hit a single culprit commit Y\*, and understanding why Y\* was broken would probably be easier.

Partly for this reason, many experienced Git users, even when working on an otherwise merge-heavy project, keep the history linear by rebasing against the latest upstream version before publishing.

**Table of Contents**

<span class="section">[Fetching individual branches](#fetching-individual-branches)</span>

<span class="section">[git fetch and fast-forwards](#fetch-fast-forwards)</span>

<span class="section">[Forcing git fetch to do non-fast-forward updates](#forcing-fetch)</span>

<span class="section">[Configuring remote-tracking branches](#remote-branch-configuration)</span>

## <span id="fetching-individual-branches"></span>Fetching individual branches

Instead of using <a href="git-remote.html" class="ulink">git-remote(1)</a>, you can also choose just to update one branch at a time, and to store it locally under an arbitrary name:

    $ git fetch origin todo:my-todo-work

The first argument, `origin`, just tells Git to fetch from the repository you originally cloned from. The second argument tells Git to fetch the branch named `todo` from the remote repository, and to store it locally under the name `refs/heads/my-todo-work`.

You can also fetch branches from other repositories; so

    $ git fetch git://example.com/proj.git master:example-master

will create a new branch named `example-master` and store in it the branch named `master` from the repository at the given URL. If you already have a branch named example-master, it will attempt to <a href="#fast-forwards" class="link" title="Fast-forward merges">fast-forward</a> to the commit given by example.com’s master branch. In more detail:

## <span id="fetch-fast-forwards"></span>git fetch and fast-forwards

In the previous example, when updating an existing branch, `git fetch` checks to make sure that the most recent commit on the remote branch is a descendant of the most recent commit on your copy of the branch before updating your copy of the branch to point at the new commit. Git calls this process a <a href="#fast-forwards" class="link" title="Fast-forward merges">fast-forward</a>.

A fast-forward looks something like this:

     o--o--o--o <-- old head of the branch
               \
                o--o--o <-- new head of the branch

In some cases it is possible that the new head will <span class="strong">**not**</span> actually be a descendant of the old head. For example, the developer may have realized she made a serious mistake, and decided to backtrack, resulting in a situation like:

     o--o--o--o--a--b <-- old head of the branch
               \
                o--o--o <-- new head of the branch

In this case, `git fetch` will fail, and print out a warning.

In that case, you can still force Git to update to the new head, as described in the following section. However, note that in the situation above this may mean losing the commits labeled `a` and `b`, unless you’ve already created a reference of your own pointing to them.

## <span id="forcing-fetch"></span>Forcing git fetch to do non-fast-forward updates

If git fetch fails because the new head of a branch is not a descendant of the old head, you may force the update with:

    $ git fetch git://example.com/proj.git +master:refs/remotes/example/master

Note the addition of the `+` sign. Alternatively, you can use the `-f` flag to force updates of all the fetched branches, as in:

    $ git fetch -f origin

Be aware that commits that the old version of example/master pointed at may be lost, as we saw in the previous section.

## <span id="remote-branch-configuration"></span>Configuring remote-tracking branches

We saw above that `origin` is just a shortcut to refer to the repository that you originally cloned from. This information is stored in Git configuration variables, which you can see using <a href="git-config.html" class="ulink">git-config(1)</a>:

    $ git config -l
    core.repositoryformatversion=0
    core.filemode=true
    core.logallrefupdates=true
    remote.origin.url=git://git.kernel.org/pub/scm/git/git.git
    remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
    branch.master.remote=origin
    branch.master.merge=refs/heads/master

If there are other repositories that you also use frequently, you can create similar configuration options to save typing; for example,

    $ git remote add example git://example.com/proj.git

adds the following to `.git/config`:

    [remote "example"]
            url = git://example.com/proj.git
            fetch = +refs/heads/*:refs/remotes/example/*

Also note that the above configuration can be performed by directly editing the file `.git/config` instead of using <a href="git-remote.html" class="ulink">git-remote(1)</a>.

After configuring the remote, the following three commands will do the same thing:

    $ git fetch git://example.com/proj.git +refs/heads/*:refs/remotes/example/*
    $ git fetch example +refs/heads/*:refs/remotes/example/*
    $ git fetch example

See <a href="git-config.html" class="ulink">git-config(1)</a> for more details on the configuration options mentioned above and <a href="git-fetch.html" class="ulink">git-fetch(1)</a> for more details on the refspec syntax.

**Table of Contents**

<span class="section">[The Object Database](#the-object-database)</span>

<span class="section">[Commit Object](#commit-object)</span>

<span class="section">[Tree Object](#tree-object)</span>

<span class="section">[Blob Object](#blob-object)</span>

<span class="section">[Trust](#trust)</span>

<span class="section">[Tag Object](#tag-object)</span>

<span class="section">[How Git stores objects efficiently: pack files](#pack-files)</span>

<span class="section">[Dangling objects](#dangling-objects)</span>

<span class="section">[Recovering from repository corruption](#recovering-from-repository-corruption)</span>

<span class="section">[The index](#the-index)</span>

Git is built on a small number of simple but powerful ideas. While it is possible to get things done without understanding them, you will find Git much more intuitive if you do.

We start with the most important, the <a href="#def_object_database" class="link">object database</a> and the <a href="#def_index" class="link">index</a>.

## <span id="the-object-database"></span>The Object Database

We already saw in <a href="#understanding-commits" class="xref" title="Understanding History: Commits">the section called “Understanding History: Commits”</a> that all commits are stored under a 40-digit "object name". In fact, all the information needed to represent the history of a project is stored in objects with such names. In each case the name is calculated by taking the SHA-1 hash of the contents of the object. The SHA-1 hash is a cryptographic hash function. What that means to us is that it is impossible to find two different objects with the same name. This has a number of advantages; among others:

- Git can quickly determine whether two objects are identical or not, just by comparing names.
- Since object names are computed the same way in every repository, the same content stored in two repositories will always be stored under the same name.
- Git can detect errors when it reads an object, by checking that the object’s name is still the SHA-1 hash of its contents.

(See <a href="#object-details" class="xref" title="Object storage format">the section called “Object storage format”</a> for the details of the object formatting and SHA-1 calculation.)

There are four different types of objects: "blob", "tree", "commit", and "tag".

- A <a href="#def_blob_object" class="link">"blob" object</a> is used to store file data.
- A <a href="#def_tree_object" class="link">"tree" object</a> ties one or more "blob" objects into a directory structure. In addition, a tree object can refer to other tree objects, thus creating a directory hierarchy.
- A <a href="#def_commit_object" class="link">"commit" object</a> ties such directory hierarchies together into a <a href="#def_DAG" class="link">directed acyclic graph</a> of revisions—​each commit contains the object name of exactly one tree designating the directory hierarchy at the time of the commit. In addition, a commit refers to "parent" commit objects that describe the history of how we arrived at that directory hierarchy.
- A <a href="#def_tag_object" class="link">"tag" object</a> symbolically identifies and can be used to sign other objects. It contains the object name and type of another object, a symbolic name (of course!) and, optionally, a signature.

The object types in some more detail:

### <span id="commit-object"></span>Commit Object

The "commit" object links a physical state of a tree with a description of how we got there and why. Use the `--pretty=raw` option to <a href="git-show.html" class="ulink">git-show(1)</a> or <a href="git-log.html" class="ulink">git-log(1)</a> to examine your favorite commit:

    $ git show -s --pretty=raw 2be7fcb476
    commit 2be7fcb4764f2dbcee52635b91fedb1b3dcf7ab4
    tree fb3a8bdd0ceddd019615af4d57a53f43d8cee2bf
    parent 257a84d9d02e90447b149af58b271c19405edb6a
    author Dave Watson <dwatson@mimvista.com> 1187576872 -0400
    committer Junio C Hamano <gitster@pobox.com> 1187591163 -0700

        Fix misspelling of 'suppress' in docs

        Signed-off-by: Junio C Hamano <gitster@pobox.com>

As you can see, a commit is defined by:

- a tree: The SHA-1 name of a tree object (as defined below), representing the contents of a directory at a certain point in time.
- parent(s): The SHA-1 name(s) of some number of commits which represent the immediately previous step(s) in the history of the project. The example above has one parent; merge commits may have more than one. A commit with no parents is called a "root" commit, and represents the initial revision of a project. Each project must have at least one root. A project can also have multiple roots, though that isn’t common (or necessarily a good idea).
- an author: The name of the person responsible for this change, together with its date.
- a committer: The name of the person who actually created the commit, with the date it was done. This may be different from the author, for example, if the author was someone who wrote a patch and emailed it to the person who used it to create the commit.
- a comment describing this commit.

Note that a commit does not itself contain any information about what actually changed; all changes are calculated by comparing the contents of the tree referred to by this commit with the trees associated with its parents. In particular, Git does not attempt to record file renames explicitly, though it can identify cases where the existence of the same file data at changing paths suggests a rename. (See, for example, the `-M` option to <a href="git-diff.html" class="ulink">git-diff(1)</a>).

A commit is usually created by <a href="git-commit.html" class="ulink">git-commit(1)</a>, which creates a commit whose parent is normally the current HEAD, and whose tree is taken from the content currently stored in the index.

### <span id="tree-object"></span>Tree Object

The ever-versatile <a href="git-show.html" class="ulink">git-show(1)</a> command can also be used to examine tree objects, but <a href="git-ls-tree.html" class="ulink">git-ls-tree(1)</a> will give you more details:

    $ git ls-tree fb3a8bdd0ce
    100644 blob 63c918c667fa005ff12ad89437f2fdc80926e21c    .gitignore
    100644 blob 5529b198e8d14decbe4ad99db3f7fb632de0439d    .mailmap
    100644 blob 6ff87c4664981e4397625791c8ea3bbb5f2279a3    COPYING
    040000 tree 2fb783e477100ce076f6bf57e4a6f026013dc745    Documentation
    100755 blob 3c0032cec592a765692234f1cba47dfdcc3a9200    GIT-VERSION-GEN
    100644 blob 289b046a443c0647624607d471289b2c7dcd470b    INSTALL
    100644 blob 4eb463797adc693dc168b926b6932ff53f17d0b1    Makefile
    100644 blob 548142c327a6790ff8821d67c2ee1eff7a656b52    README
    ...

As you can see, a tree object contains a list of entries, each with a mode, object type, SHA-1 name, and name, sorted by name. It represents the contents of a single directory tree.

The object type may be a blob, representing the contents of a file, or another tree, representing the contents of a subdirectory. Since trees and blobs, like all other objects, are named by the SHA-1 hash of their contents, two trees have the same SHA-1 name if and only if their contents (including, recursively, the contents of all subdirectories) are identical. This allows Git to quickly determine the differences between two related tree objects, since it can ignore any entries with identical object names.

(Note: in the presence of submodules, trees may also have commits as entries. See <a href="#submodules" class="xref" title="Chapter 8. Submodules">Chapter 8, <em>Submodules</em></a> for documentation.)

Note that the files all have mode 644 or 755: Git actually only pays attention to the executable bit.

### <span id="blob-object"></span>Blob Object

You can use <a href="git-show.html" class="ulink">git-show(1)</a> to examine the contents of a blob; take, for example, the blob in the entry for `COPYING` from the tree above:

    $ git show 6ff87c4664

     Note that the only valid version of the GPL as far as this project
     is concerned is _this_ particular version of the license (ie v2, not
     v2.2 or v3.x or whatever), unless explicitly otherwise stated.
    ...

A "blob" object is nothing but a binary blob of data. It doesn’t refer to anything else or have attributes of any kind.

Since the blob is entirely defined by its data, if two files in a directory tree (or in multiple different versions of the repository) have the same contents, they will share the same blob object. The object is totally independent of its location in the directory tree, and renaming a file does not change the object that file is associated with.

Note that any tree or blob object can be examined using <a href="git-show.html" class="ulink">git-show(1)</a> with the &lt;revision&gt;:&lt;path&gt; syntax. This can sometimes be useful for browsing the contents of a tree that is not currently checked out.

### <span id="trust"></span>Trust

If you receive the SHA-1 name of a blob from one source, and its contents from another (possibly untrusted) source, you can still trust that those contents are correct as long as the SHA-1 name agrees. This is because the SHA-1 is designed so that it is infeasible to find different contents that produce the same hash.

Similarly, you need only trust the SHA-1 name of a top-level tree object to trust the contents of the entire directory that it refers to, and if you receive the SHA-1 name of a commit from a trusted source, then you can easily verify the entire history of commits reachable through parents of that commit, and all of those contents of the trees referred to by those commits.

So to introduce some real trust in the system, the only thing you need to do is to digitally sign just <span class="emphasis">_one_</span> special note, which includes the name of a top-level commit. Your digital signature shows others that you trust that commit, and the immutability of the history of commits tells others that they can trust the whole history.

In other words, you can easily validate a whole archive by just sending out a single email that tells the people the name (SHA-1 hash) of the top commit, and digitally sign that email using something like GPG/PGP.

To assist in this, Git also provides the tag object…​

### <span id="tag-object"></span>Tag Object

A tag object contains an object, object type, tag name, the name of the person ("tagger") who created the tag, and a message, which may contain a signature, as can be seen using <a href="git-cat-file.html" class="ulink">git-cat-file(1)</a>:

    $ git cat-file tag v1.5.0
    object 437b1b20df4b356c9342dac8d38849f24ef44f27
    type commit
    tag v1.5.0
    tagger Junio C Hamano <junkio@cox.net> 1171411200 +0000

    GIT 1.5.0
    -----BEGIN PGP SIGNATURE-----
    Version: GnuPG v1.4.6 (GNU/Linux)

    iD8DBQBF0lGqwMbZpPMRm5oRAuRiAJ9ohBLd7s2kqjkKlq1qqC57SbnmzQCdG4ui
    nLE/L9aUXdWeTFPron96DLA=
    =2E+0
    -----END PGP SIGNATURE-----

See the <a href="git-tag.html" class="ulink">git-tag(1)</a> command to learn how to create and verify tag objects. (Note that <a href="git-tag.html" class="ulink">git-tag(1)</a> can also be used to create "lightweight tags", which are not tag objects at all, but just simple references whose names begin with `refs/tags/`).

### <span id="pack-files"></span>How Git stores objects efficiently: pack files

Newly created objects are initially created in a file named after the object’s SHA-1 hash (stored in `.git/objects`).

Unfortunately this system becomes inefficient once a project has a lot of objects. Try this on an old project:

    $ git count-objects
    6930 objects, 47620 kilobytes

The first number is the number of objects which are kept in individual files. The second is the amount of space taken up by those "loose" objects.

You can save space and make Git faster by moving these loose objects in to a "pack file", which stores a group of objects in an efficient compressed format; the details of how pack files are formatted can be found in <a href="technical/pack-format.html" class="ulink">pack format</a>.

To put the loose objects into a pack, just run git repack:

    $ git repack
    Counting objects: 6020, done.
    Delta compression using up to 4 threads.
    Compressing objects: 100% (6020/6020), done.
    Writing objects: 100% (6020/6020), done.
    Total 6020 (delta 4070), reused 0 (delta 0)

This creates a single "pack file" in .git/objects/pack/ containing all currently unpacked objects. You can then run

    $ git prune

to remove any of the "loose" objects that are now contained in the pack. This will also remove any unreferenced objects (which may be created when, for example, you use `git reset` to remove a commit). You can verify that the loose objects are gone by looking at the `.git/objects` directory or by running

    $ git count-objects
    0 objects, 0 kilobytes

Although the object files are gone, any commands that refer to those objects will work exactly as they did before.

The <a href="git-gc.html" class="ulink">git-gc(1)</a> command performs packing, pruning, and more for you, so is normally the only high-level command you need.

### <span id="dangling-objects"></span>Dangling objects

The <a href="git-fsck.html" class="ulink">git-fsck(1)</a> command will sometimes complain about dangling objects. They are not a problem.

The most common cause of dangling objects is that you’ve rebased a branch, or you have pulled from somebody else who rebased a branch—​see <a href="#cleaning-up-history" class="xref" title="Chapter 5. Rewriting history and maintaining patch series">Chapter 5, <em>Rewriting history and maintaining patch series</em></a>. In that case, the old head of the original branch still exists, as does everything it pointed to. The branch pointer itself just doesn’t, since you replaced it with another one.

There are also other situations that cause dangling objects. For example, a "dangling blob" may arise because you did a `git add` of a file, but then, before you actually committed it and made it part of the bigger picture, you changed something else in that file and committed that <span class="strong">**updated**</span> thing—​the old state that you added originally ends up not being pointed to by any commit or tree, so it’s now a dangling blob object.

Similarly, when the "recursive" merge strategy runs, and finds that there are criss-cross merges and thus more than one merge base (which is fairly unusual, but it does happen), it will generate one temporary midway tree (or possibly even more, if you had lots of criss-crossing merges and more than two merge bases) as a temporary internal merge base, and again, those are real objects, but the end result will not end up pointing to them, so they end up "dangling" in your repository.

Generally, dangling objects aren’t anything to worry about. They can even be very useful: if you screw something up, the dangling objects can be how you recover your old tree (say, you did a rebase, and realized that you really didn’t want to—​you can look at what dangling objects you have, and decide to reset your head to some old dangling state).

For commits, you can just use:

    $ gitk <dangling-commit-sha-goes-here> --not --all

This asks for all the history reachable from the given commit but not from any branch, tag, or other reference. If you decide it’s something you want, you can always create a new reference to it, e.g.,

    $ git branch recovered-branch <dangling-commit-sha-goes-here>

For blobs and trees, you can’t do the same, but you can still examine them. You can just do

    $ git show <dangling-blob/tree-sha-goes-here>

to show what the contents of the blob were (or, for a tree, basically what the `ls` for that directory was), and that may give you some idea of what the operation was that left that dangling object.

Usually, dangling blobs and trees aren’t very interesting. They’re almost always the result of either being a half-way mergebase (the blob will often even have the conflict markers from a merge in it, if you have had conflicting merges that you fixed up by hand), or simply because you interrupted a `git fetch` with ^C or something like that, leaving <span class="emphasis">_some_</span> of the new objects in the object database, but just dangling and useless.

Anyway, once you are sure that you’re not interested in any dangling state, you can just prune all unreachable objects:

    $ git prune

and they’ll be gone. (You should only run `git prune` on a quiescent repository—​it’s kind of like doing a filesystem fsck recovery: you don’t want to do that while the filesystem is mounted. `git prune` is designed not to cause any harm in such cases of concurrent accesses to a repository but you might receive confusing or scary messages.)

### <span id="recovering-from-repository-corruption"></span>Recovering from repository corruption

By design, Git treats data trusted to it with caution. However, even in the absence of bugs in Git itself, it is still possible that hardware or operating system errors could corrupt data.

The first defense against such problems is backups. You can back up a Git directory using clone, or just using cp, tar, or any other backup mechanism.

As a last resort, you can search for the corrupted objects and attempt to replace them by hand. Back up your repository before attempting this in case you corrupt things even more in the process.

We’ll assume that the problem is a single missing or corrupted blob, which is sometimes a solvable problem. (Recovering missing trees and especially commits is <span class="strong">**much**</span> harder).

Before starting, verify that there is corruption, and figure out where it is with <a href="git-fsck.html" class="ulink">git-fsck(1)</a>; this may be time-consuming.

Assume the output looks like this:

    $ git fsck --full --no-dangling
    broken link from    tree 2d9263c6d23595e7cb2a21e5ebbb53655278dff8
                  to    blob 4b9458b3786228369c63936db65827de3cc06200
    missing blob 4b9458b3786228369c63936db65827de3cc06200

Now you know that blob 4b9458b3 is missing, and that the tree 2d9263c6 points to it. If you could find just one copy of that missing blob object, possibly in some other repository, you could move it into `.git/objects/4b/9458b3...` and be done. Suppose you can’t. You can still examine the tree that pointed to it with <a href="git-ls-tree.html" class="ulink">git-ls-tree(1)</a>, which might output something like:

    $ git ls-tree 2d9263c6d23595e7cb2a21e5ebbb53655278dff8
    100644 blob 8d14531846b95bfa3564b58ccfb7913a034323b8    .gitignore
    100644 blob ebf9bf84da0aab5ed944264a5db2a65fe3a3e883    .mailmap
    100644 blob ca442d313d86dc67e0a2e5d584b465bd382cbf5c    COPYING
    ...
    100644 blob 4b9458b3786228369c63936db65827de3cc06200    myfile
    ...

So now you know that the missing blob was the data for a file named `myfile`. And chances are you can also identify the directory—​let’s say it’s in `somedirectory`. If you’re lucky the missing copy might be the same as the copy you have checked out in your working tree at `somedirectory/myfile`; you can test whether that’s right with <a href="git-hash-object.html" class="ulink">git-hash-object(1)</a>:

    $ git hash-object -w somedirectory/myfile

which will create and store a blob object with the contents of somedirectory/myfile, and output the SHA-1 of that object. if you’re extremely lucky it might be 4b9458b3786228369c63936db65827de3cc06200, in which case you’ve guessed right, and the corruption is fixed!

Otherwise, you need more information. How do you tell which version of the file has been lost?

The easiest way to do this is with:

    $ git log --raw --all --full-history -- somedirectory/myfile

Because you’re asking for raw output, you’ll now get something like

    commit abc
    Author:
    Date:
    ...
    :100644 100644 4b9458b newsha M somedirectory/myfile


    commit xyz
    Author:
    Date:

    ...
    :100644 100644 oldsha 4b9458b M somedirectory/myfile

This tells you that the immediately following version of the file was "newsha", and that the immediately preceding version was "oldsha". You also know the commit messages that went with the change from oldsha to 4b9458b and with the change from 4b9458b to newsha.

If you’ve been committing small enough changes, you may now have a good shot at reconstructing the contents of the in-between state 4b9458b.

If you can do that, you can now recreate the missing object with

    $ git hash-object -w <recreated-file>

and your repository is good again!

(Btw, you could have ignored the `fsck`, and started with doing a

    $ git log --raw --all

and just looked for the sha of the missing object (4b9458b) in that whole thing. It’s up to you—​Git does <span class="strong">**have**</span> a lot of information, it is just missing one particular blob version.

## <span id="the-index"></span>The index

The index is a binary file (generally kept in `.git/index`) containing a sorted list of path names, each with permissions and the SHA-1 of a blob object; <a href="git-ls-files.html" class="ulink">git-ls-files(1)</a> can show you the contents of the index:

    $ git ls-files --stage
    100644 63c918c667fa005ff12ad89437f2fdc80926e21c 0       .gitignore
    100644 5529b198e8d14decbe4ad99db3f7fb632de0439d 0       .mailmap
    100644 6ff87c4664981e4397625791c8ea3bbb5f2279a3 0       COPYING
    100644 a37b2152bd26be2c2289e1f57a292534a51a93c7 0       Documentation/.gitignore
    100644 fbefe9a45b00a54b58d94d06eca48b03d40a50e0 0       Documentation/Makefile
    ...
    100644 2511aef8d89ab52be5ec6a5e46236b4b6bcd07ea 0       xdiff/xtypes.h
    100644 2ade97b2574a9f77e7ae4002a4e07a6a38e46d07 0       xdiff/xutils.c
    100644 d5de8292e05e7c36c4b68857c1cf9855e3d2f70a 0       xdiff/xutils.h

Note that in older documentation you may see the index called the "current directory cache" or just the "cache". It has three important properties:

1.  The index contains all the information necessary to generate a single (uniquely determined) tree object.

    For example, running <a href="git-commit.html" class="ulink">git-commit(1)</a> generates this tree object from the index, stores it in the object database, and uses it as the tree object associated with the new commit.

2.  The index enables fast comparisons between the tree object it defines and the working tree.

    It does this by storing some additional data for each entry (such as the last modified time). This data is not displayed above, and is not stored in the created tree object, but it can be used to determine quickly which files in the working directory differ from what was stored in the index, and thus save Git from having to read all of the data from such files to look for changes.

3.  It can efficiently represent information about merge conflicts between different tree objects, allowing each pathname to be associated with sufficient information about the trees involved that you can create a three-way merge between them.

    We saw in <a href="#conflict-resolution" class="xref" title="Getting conflict-resolution help during a merge">the section called “Getting conflict-resolution help during a merge”</a> that during a merge the index can store multiple versions of a single file (called "stages"). The third column in the <a href="git-ls-files.html" class="ulink">git-ls-files(1)</a> output above is the stage number, and will take on values other than 0 for files with merge conflicts.

The index is thus a sort of temporary staging area, which is filled with a tree which you are in the process of working on.

If you blow the index away entirely, you generally haven’t lost any information as long as you have the name of the tree that it described.

**Table of Contents**

<span class="section">[Pitfalls with submodules](#pitfalls-with-submodules)</span>

Large projects are often composed of smaller, self-contained modules. For example, an embedded Linux distribution’s source tree would include every piece of software in the distribution with some local modifications; a movie player might need to build against a specific, known-working version of a decompression library; several independent programs might all share the same build scripts.

With centralized revision control systems this is often accomplished by including every module in one single repository. Developers can check out all modules or only the modules they need to work with. They can even modify files across several modules in a single commit while moving things around or updating APIs and translations.

Git does not allow partial checkouts, so duplicating this approach in Git would force developers to keep a local copy of modules they are not interested in touching. Commits in an enormous checkout would be slower than you’d expect as Git would have to scan every directory for changes. If modules have a lot of local history, clones would take forever.

On the plus side, distributed revision control systems can much better integrate with external sources. In a centralized model, a single arbitrary snapshot of the external project is exported from its own revision control and then imported into the local revision control on a vendor branch. All the history is hidden. With distributed revision control you can clone the entire external history and much more easily follow development and re-merge local changes.

Git’s submodule support allows a repository to contain, as a subdirectory, a checkout of an external project. Submodules maintain their own identity; the submodule support just stores the submodule repository location and commit ID, so other developers who clone the containing project ("superproject") can easily clone all the submodules at the same revision. Partial checkouts of the superproject are possible: you can tell Git to clone none, some or all of the submodules.

The <a href="git-submodule.html" class="ulink">git-submodule(1)</a> command is available since Git 1.5.3. Users with Git 1.5.2 can look up the submodule commits in the repository and manually check them out; earlier versions won’t recognize the submodules at all.

To see how submodule support works, create four example repositories that can be used later as a submodule:

    $ mkdir ~/git
    $ cd ~/git
    $ for i in a b c d
    do
            mkdir $i
            cd $i
            git init
            echo "module $i" > $i.txt
            git add $i.txt
            git commit -m "Initial commit, submodule $i"
            cd ..
    done

Now create the superproject and add all the submodules:

    $ mkdir super
    $ cd super
    $ git init
    $ for i in a b c d
    do
            git submodule add ~/git/$i $i
    done

### Note

Do not use local URLs here if you plan to publish your superproject!

See what files `git submodule` created:

    $ ls -a
    .  ..  .git  .gitmodules  a  b  c  d

The `git submodule add <repo> <path>` command does a couple of things:

- It clones the submodule from `<repo>` to the given `<path>` under the current directory and by default checks out the master branch.
- It adds the submodule’s clone path to the <a href="gitmodules.html" class="ulink">gitmodules(5)</a> file and adds this file to the index, ready to be committed.
- It adds the submodule’s current commit ID to the index, ready to be committed.

Commit the superproject:

    $ git commit -m "Add submodules a, b, c and d."

Now clone the superproject:

    $ cd ..
    $ git clone super cloned
    $ cd cloned

The submodule directories are there, but they’re empty:

    $ ls -a a
    .  ..
    $ git submodule status
    -d266b9873ad50488163457f025db7cdd9683d88b a
    -e81d457da15309b4fef4249aba9b50187999670d b
    -c1536a972b9affea0f16e0680ba87332dc059146 c
    -d96249ff5d57de5de093e6baff9e0aafa5276a74 d

### Note

The commit object names shown above would be different for you, but they should match the HEAD commit object names of your repositories. You can check it by running `git ls-remote ../a`.

Pulling down the submodules is a two-step process. First run `git submodule init` to add the submodule repository URLs to `.git/config`:

    $ git submodule init

Now use `git submodule update` to clone the repositories and check out the commits specified in the superproject:

    $ git submodule update
    $ cd a
    $ ls -a
    .  ..  .git  a.txt

One major difference between `git submodule update` and `git submodule add` is that `git submodule update` checks out a specific commit, rather than the tip of a branch. It’s like checking out a tag: the head is detached, so you’re not working on a branch.

    $ git branch
    * (detached from d266b98)
      master

If you want to make a change within a submodule and you have a detached head, then you should create or checkout a branch, make your changes, publish the change within the submodule, and then update the superproject to reference the new commit:

    $ git switch master

or

    $ git switch -c fix-up

then

    $ echo "adding a line again" >> a.txt
    $ git commit -a -m "Updated the submodule from within the superproject."
    $ git push
    $ cd ..
    $ git diff
    diff --git a/a b/a
    index d266b98..261dfac 160000
    --- a/a
    +++ b/a
    @@ -1 +1 @@
    -Subproject commit d266b9873ad50488163457f025db7cdd9683d88b
    +Subproject commit 261dfac35cb99d380eb966e102c1197139f7fa24
    $ git add a
    $ git commit -m "Updated submodule a."
    $ git push

You have to run `git submodule update` after `git pull` if you want to update submodules, too.

## <span id="pitfalls-with-submodules"></span>Pitfalls with submodules

Always publish the submodule change before publishing the change to the superproject that references it. If you forget to publish the submodule change, others won’t be able to clone the repository:

    $ cd ~/git/super/a
    $ echo i added another line to this file >> a.txt
    $ git commit -a -m "doing it wrong this time"
    $ cd ..
    $ git add a
    $ git commit -m "Updated submodule a again."
    $ git push
    $ cd ~/git/cloned
    $ git pull
    $ git submodule update
    error: pathspec '261dfac35cb99d380eb966e102c1197139f7fa24' did not match any file(s) known to git.
    Did you forget to 'git add'?
    Unable to checkout '261dfac35cb99d380eb966e102c1197139f7fa24' in submodule path 'a'

In older Git versions it could be easily forgotten to commit new or modified files in a submodule, which silently leads to similar problems as not pushing the submodule changes. Starting with Git 1.7.0 both `git status` and `git diff` in the superproject show submodules as modified when they contain new or modified files to protect against accidentally committing such a state. `git diff` will also add a `-dirty` to the work tree side when generating patch output or used with the `--submodule` option:

    $ git diff
    diff --git a/sub b/sub
    --- a/sub
    +++ b/sub
    @@ -1 +1 @@
    -Subproject commit 3f356705649b5d566d97ff843cf193359229a453
    +Subproject commit 3f356705649b5d566d97ff843cf193359229a453-dirty
    $ git diff --submodule
    Submodule sub 3f35670..3f35670-dirty:

You also should not rewind branches in a submodule beyond commits that were ever recorded in any superproject.

It’s not safe to run `git submodule update` if you’ve made and committed changes within a submodule without checking out a branch first. They will be silently overwritten:

    $ cat a.txt
    module a
    $ echo line added from private2 >> a.txt
    $ git commit -a -m "line added inside private2"
    $ cd ..
    $ git submodule update
    Submodule path 'a': checked out 'd266b9873ad50488163457f025db7cdd9683d88b'
    $ cd a
    $ cat a.txt
    module a

### Note

The changes are still visible in the submodule’s reflog.

If you have uncommitted changes in your submodule working tree, `git submodule update` will not overwrite them. Instead, you get the usual warning about not being able switch from a dirty branch.

**Table of Contents**

<span class="section">[Object access and manipulation](#object-manipulation)</span>

<span class="section">[The Workflow](#the-workflow)</span>

<span class="section">[working directory → index](#working-directory-to-index)</span>

<span class="section">[index → object database](#index-to-object-database)</span>

<span class="section">[object database → index](#object-database-to-index)</span>

<span class="section">[index → working directory](#index-to-working-directory)</span>

<span class="section">[Tying it all together](#tying-it-all-together)</span>

<span class="section">[Examining the data](#examining-the-data)</span>

<span class="section">[Merging multiple trees](#merging-multiple-trees)</span>

<span class="section">[Merging multiple trees, continued](#merging-multiple-trees-2)</span>

Many of the higher-level commands were originally implemented as shell scripts using a smaller core of low-level Git commands. These can still be useful when doing unusual things with Git, or just as a way to understand its inner workings.

## <span id="object-manipulation"></span>Object access and manipulation

The <a href="git-cat-file.html" class="ulink">git-cat-file(1)</a> command can show the contents of any object, though the higher-level <a href="git-show.html" class="ulink">git-show(1)</a> is usually more useful.

The <a href="git-commit-tree.html" class="ulink">git-commit-tree(1)</a> command allows constructing commits with arbitrary parents and trees.

A tree can be created with <a href="git-write-tree.html" class="ulink">git-write-tree(1)</a> and its data can be accessed by <a href="git-ls-tree.html" class="ulink">git-ls-tree(1)</a>. Two trees can be compared with <a href="git-diff-tree.html" class="ulink">git-diff-tree(1)</a>.

A tag is created with <a href="git-mktag.html" class="ulink">git-mktag(1)</a>, and the signature can be verified by <a href="git-verify-tag.html" class="ulink">git-verify-tag(1)</a>, though it is normally simpler to use <a href="git-tag.html" class="ulink">git-tag(1)</a> for both.

## <span id="the-workflow"></span>The Workflow

High-level operations such as <a href="git-commit.html" class="ulink">git-commit(1)</a> and <a href="git-restore.html" class="ulink">git-restore(1)</a> work by moving data between the working tree, the index, and the object database. Git provides low-level operations which perform each of these steps individually.

Generally, all Git operations work on the index file. Some operations work <span class="strong">**purely**</span> on the index file (showing the current state of the index), but most operations move data between the index file and either the database or the working directory. Thus there are four main combinations:

### <span id="working-directory-to-index"></span>working directory → index

The <a href="git-update-index.html" class="ulink">git-update-index(1)</a> command updates the index with information from the working directory. You generally update the index information by just specifying the filename you want to update, like so:

    $ git update-index filename

but to avoid common mistakes with filename globbing etc., the command will not normally add totally new entries or remove old entries, i.e. it will normally just update existing cache entries.

To tell Git that yes, you really do realize that certain files no longer exist, or that new files should be added, you should use the `--remove` and `--add` flags respectively.

NOTE! A `--remove` flag does <span class="emphasis">_not_</span> mean that subsequent filenames will necessarily be removed: if the files still exist in your directory structure, the index will be updated with their new status, not removed. The only thing `--remove` means is that update-index will be considering a removed file to be a valid thing, and if the file really does not exist any more, it will update the index accordingly.

As a special case, you can also do `git update-index --refresh`, which will refresh the "stat" information of each index to match the current stat information. It will <span class="emphasis">_not_</span> update the object status itself, and it will only update the fields that are used to quickly test whether an object still matches its old backing store object.

The previously introduced <a href="git-add.html" class="ulink">git-add(1)</a> is just a wrapper for <a href="git-update-index.html" class="ulink">git-update-index(1)</a>.

### <span id="index-to-object-database"></span>index → object database

You write your current index file to a "tree" object with the program

    $ git write-tree

that doesn’t come with any options—​it will just write out the current index into the set of tree objects that describe that state, and it will return the name of the resulting top-level tree. You can use that tree to re-generate the index at any time by going in the other direction:

### <span id="object-database-to-index"></span>object database → index

You read a "tree" file from the object database, and use that to populate (and overwrite—​don’t do this if your index contains any unsaved state that you might want to restore later!) your current index. Normal operation is just

    $ git read-tree <SHA-1 of tree>

and your index file will now be equivalent to the tree that you saved earlier. However, that is only your <span class="emphasis">_index_</span> file: your working directory contents have not been modified.

### <span id="index-to-working-directory"></span>index → working directory

You update your working directory from the index by "checking out" files. This is not a very common operation, since normally you’d just keep your files updated, and rather than write to your working directory, you’d tell the index files about the changes in your working directory (i.e. `git update-index`).

However, if you decide to jump to a new version, or check out somebody else’s version, or just restore a previous tree, you’d populate your index file with read-tree, and then you need to check out the result with

    $ git checkout-index filename

or, if you want to check out all of the index, use `-a`.

NOTE! `git checkout-index` normally refuses to overwrite old files, so if you have an old version of the tree already checked out, you will need to use the `-f` flag (<span class="emphasis">_before_</span> the `-a` flag or the filename) to <span class="emphasis">_force_</span> the checkout.

Finally, there are a few odds and ends which are not purely moving from one representation to the other:

### <span id="tying-it-all-together"></span>Tying it all together

To commit a tree you have instantiated with `git write-tree`, you’d create a "commit" object that refers to that tree and the history behind it—​most notably the "parent" commits that preceded it in history.

Normally a "commit" has one parent: the previous state of the tree before a certain change was made. However, sometimes it can have two or more parent commits, in which case we call it a "merge", due to the fact that such a commit brings together ("merges") two or more previous states represented by other commits.

In other words, while a "tree" represents a particular directory state of a working directory, a "commit" represents that state in time, and explains how we got there.

You create a commit object by giving it the tree that describes the state at the time of the commit, and a list of parents:

    $ git commit-tree <tree> -p <parent> [(-p <parent2>)...]

and then giving the reason for the commit on stdin (either through redirection from a pipe or file, or by just typing it at the tty).

`git commit-tree` will return the name of the object that represents that commit, and you should save it away for later use. Normally, you’d commit a new `HEAD` state, and while Git doesn’t care where you save the note about that state, in practice we tend to just write the result to the file pointed at by `.git/HEAD`, so that we can always see what the last committed state was.

Here is a picture that illustrates how various pieces fit together:

                         commit-tree
                          commit obj
                           +----+
                           |    |
                           |    |
                           V    V
                        +-----------+
                        | Object DB |
                        |  Backing  |
                        |   Store   |
                        +-----------+
                           ^
               write-tree  |     |
                 tree obj  |     |
                           |     |  read-tree
                           |     |  tree obj
                                 V
                        +-----------+
                        |   Index   |
                        |  "cache"  |
                        +-----------+
             update-index  ^
                 blob obj  |     |
                           |     |
        checkout-index -u  |     |  checkout-index
                 stat      |     |  blob obj
                                 V
                        +-----------+
                        |  Working  |
                        | Directory |
                        +-----------+

## <span id="examining-the-data"></span>Examining the data

You can examine the data represented in the object database and the index with various helper tools. For every object, you can use <a href="git-cat-file.html" class="ulink">git-cat-file(1)</a> to examine details about the object:

    $ git cat-file -t <objectname>

shows the type of the object, and once you have the type (which is usually implicit in where you find the object), you can use

    $ git cat-file blob|tree|commit|tag <objectname>

to show its contents. NOTE! Trees have binary content, and as a result there is a special helper for showing that content, called `git ls-tree`, which turns the binary content into a more easily readable form.

It’s especially instructive to look at "commit" objects, since those tend to be small and fairly self-explanatory. In particular, if you follow the convention of having the top commit name in `.git/HEAD`, you can do

    $ git cat-file commit HEAD

to see what the top commit was.

## <span id="merging-multiple-trees"></span>Merging multiple trees

Git can help you perform a three-way merge, which can in turn be used for a many-way merge by repeating the merge procedure several times. The usual situation is that you only do one three-way merge (reconciling two lines of history) and commit the result, but if you like to, you can merge several branches in one go.

To perform a three-way merge, you start with the two commits you want to merge, find their closest common parent (a third commit), and compare the trees corresponding to these three commits.

To get the "base" for the merge, look up the common parent of two commits:

    $ git merge-base <commit1> <commit2>

This prints the name of a commit they are both based on. You should now look up the tree objects of those commits, which you can easily do with

    $ git cat-file commit <commitname> | head -1

since the tree object information is always the first line in a commit object.

Once you know the three trees you are going to merge (the one "original" tree, aka the common tree, and the two "result" trees, aka the branches you want to merge), you do a "merge" read into the index. This will complain if it has to throw away your old index contents, so you should make sure that you’ve committed those—​in fact you would normally always do a merge against your last commit (which should thus match what you have in your current index anyway).

To do the merge, do

    $ git read-tree -m -u <origtree> <yourtree> <targettree>

which will do all trivial merge operations for you directly in the index file, and you can just write the result out with `git write-tree`.

## <span id="merging-multiple-trees-2"></span>Merging multiple trees, continued

Sadly, many merges aren’t trivial. If there are files that have been added, moved or removed, or if both branches have modified the same file, you will be left with an index tree that contains "merge entries" in it. Such an index tree can <span class="emphasis">_NOT_</span> be written out to a tree object, and you will have to resolve any such merge clashes using other tools before you can write out the result.

You can examine such index state with `git ls-files --unmerged` command. An example:

    $ git read-tree -m $orig HEAD $target
    $ git ls-files --unmerged
    100644 263414f423d0e4d70dae8fe53fa34614ff3e2860 1       hello.c
    100644 06fa6a24256dc7e560efa5687fa84b51f0263c3a 2       hello.c
    100644 cc44c73eb783565da5831b4d820c962954019b69 3       hello.c

Each line of the `git ls-files --unmerged` output begins with the blob mode bits, blob SHA-1, <span class="emphasis">_stage number_</span>, and the filename. The <span class="emphasis">_stage number_</span> is Git’s way to say which tree it came from: stage 1 corresponds to the `$orig` tree, stage 2 to the `HEAD` tree, and stage 3 to the `$target` tree.

Earlier we said that trivial merges are done inside `git read-tree -m`. For example, if the file did not change from `$orig` to `HEAD` or `$target`, or if the file changed from `$orig` to `HEAD` and `$orig` to `$target` the same way, obviously the final outcome is what is in `HEAD`. What the above example shows is that file `hello.c` was changed from `$orig` to `HEAD` and `$orig` to `$target` in a different way. You could resolve this by running your favorite 3-way merge program, e.g. `diff3`, `merge`, or Git’s own merge-file, on the blob objects from these three stages yourself, like this:

    $ git cat-file blob 263414f >hello.c~1
    $ git cat-file blob 06fa6a2 >hello.c~2
    $ git cat-file blob cc44c73 >hello.c~3
    $ git merge-file hello.c~2 hello.c~1 hello.c~3

This would leave the merge result in `hello.c~2` file, along with conflict markers if there are conflicts. After verifying the merge result makes sense, you can tell Git what the final merge result for this file is by:

    $ mv -f hello.c~2 hello.c
    $ git update-index hello.c

When a path is in the "unmerged" state, running `git update-index` for that path tells Git to mark the path resolved.

The above is the description of a Git merge at the lowest level, to help you understand what conceptually happens under the hood. In practice, nobody, not even Git itself, runs `git cat-file` three times for this. There is a `git merge-index` program that extracts the stages to temporary files and calls a "merge" script on it:

    $ git merge-index git-merge-one-file hello.c

and that is what higher level `git merge -s resolve` is implemented with.

**Table of Contents**

<span class="section">[Object storage format](#object-details)</span>

<span class="section">[A birds-eye view of Git’s source code](#birdview-on-the-source-code)</span>

This chapter covers internal details of the Git implementation which probably only Git developers need to understand.

## <span id="object-details"></span>Object storage format

All objects have a statically determined "type" which identifies the format of the object (i.e. how it is used, and how it can refer to other objects). There are currently four different object types: "blob", "tree", "commit", and "tag".

Regardless of object type, all objects share the following characteristics: they are all deflated with zlib, and have a header that not only specifies their type, but also provides size information about the data in the object. It’s worth noting that the SHA-1 hash that is used to name the object is the hash of the original data plus this header, so `sha1sum` <span class="emphasis">_file_</span> does not match the object name for <span class="emphasis">_file_</span>.

As a result, the general consistency of an object can always be tested independently of the contents or the type of the object: all objects can be validated by verifying that (a) their hashes match the content of the file and (b) the object successfully inflates to a stream of bytes that forms a sequence of `<ascii type without space> + <space> + <ascii decimal size> + <byte\0> + <binary object data>`.

The structured objects can further have their structure and connectivity to other objects verified. This is generally done with the `git fsck` program, which generates a full dependency graph of all objects, and verifies their internal consistency (in addition to just verifying their superficial consistency through the hash).

## <span id="birdview-on-the-source-code"></span>A birds-eye view of Git’s source code

It is not always easy for new developers to find their way through Git’s source code. This section gives you a little guidance to show where to start.

A good place to start is with the contents of the initial commit, with:

    $ git switch --detach e83c5163

The initial revision lays the foundation for almost everything Git has today, but is small enough to read in one sitting.

Note that terminology has changed since that revision. For example, the README in that revision uses the word "changeset" to describe what we now call a <a href="#def_commit_object" class="link">commit</a>.

Also, we do not call it "cache" any more, but rather "index"; however, the file is still called `cache.h`. Remark: Not much reason to change it now, especially since there is no good single name for it anyway, because it is basically <span class="emphasis">_the_</span> header file which is included by <span class="emphasis">_all_</span> of Git’s C sources.

If you grasp the ideas in that initial commit, you should check out a more recent version and skim `cache.h`, `object.h` and `commit.h`.

In the early days, Git (in the tradition of UNIX) was a bunch of programs which were extremely simple, and which you used in scripts, piping the output of one into another. This turned out to be good for initial development, since it was easier to test new things. However, recently many of these parts have become builtins, and some of the core has been "libified", i.e. put into libgit.a for performance, portability reasons, and to avoid code duplication.

By now, you know what the index is (and find the corresponding data structures in `cache.h`), and that there are just a couple of object types (blobs, trees, commits and tags) which inherit their common structure from `struct object`, which is their first member (and thus, you can cast e.g. `(struct object *)commit` to achieve the <span class="emphasis">_same_</span> as `&commit->object`, i.e. get at the object name and flags).

Now is a good point to take a break to let this information sink in.

Next step: get familiar with the object naming. Read <a href="#naming-commits" class="xref" title="Naming commits">the section called “Naming commits”</a>. There are quite a few ways to name an object (and not only revisions!). All of these are handled in `sha1_name.c`. Just have a quick look at the function `get_sha1()`. A lot of the special handling is done by functions like `get_sha1_basic()` or the likes.

This is just to get you into the groove for the most libified part of Git: the revision walker.

Basically, the initial version of `git log` was a shell script:

    $ git-rev-list --pretty $(git-rev-parse --default HEAD "$@") | \
            LESS=-S ${PAGER:-less}

What does this mean?

`git rev-list` is the original version of the revision walker, which <span class="emphasis">_always_</span> printed a list of revisions to stdout. It is still functional, and needs to, since most new Git commands start out as scripts using `git rev-list`.

`git rev-parse` is not as important any more; it was only used to filter out options that were relevant for the different plumbing commands that were called by the script.

Most of what `git rev-list` did is contained in `revision.c` and `revision.h`. It wraps the options in a struct named `rev_info`, which controls how and what revisions are walked, and more.

The original job of `git rev-parse` is now taken by the function `setup_revisions()`, which parses the revisions and the common command-line options for the revision walker. This information is stored in the struct `rev_info` for later consumption. You can do your own command-line option parsing after calling `setup_revisions()`. After that, you have to call `prepare_revision_walk()` for initialization, and then you can get the commits one by one with the function `get_revision()`.

If you are interested in more details of the revision walking process, just have a look at the first implementation of `cmd_log()`; call `git show v1.3.0~155^2~4` and scroll down to that function (note that you no longer need to call `setup_pager()` directly).

Nowadays, `git log` is a builtin, which means that it is <span class="emphasis">_contained_</span> in the command `git`. The source side of a builtin is

- a function called `cmd_<bla>`, typically defined in `builtin/<bla.c>` (note that older versions of Git used to have it in `builtin-<bla>.c` instead), and declared in `builtin.h`.
- an entry in the `commands[]` array in `git.c`, and
- an entry in `BUILTIN_OBJECTS` in the `Makefile`.

Sometimes, more than one builtin is contained in one source file. For example, `cmd_whatchanged()` and `cmd_log()` both reside in `builtin/log.c`, since they share quite a bit of code. In that case, the commands which are <span class="emphasis">_not_</span> named like the `.c` file in which they live have to be listed in `BUILT_INS` in the `Makefile`.

`git log` looks more complicated in C than it does in the original script, but that allows for a much greater flexibility and performance.

Here again it is a good point to take a pause.

Lesson three is: study the code. Really, it is the best way to learn about the organization of Git (after you know the basic concepts).

So, think about something which you are interested in, say, "how can I access a blob just knowing the object name of it?". The first step is to find a Git command with which you can do it. In this example, it is either `git show` or `git cat-file`.

For the sake of clarity, let’s stay with `git cat-file`, because it

- is plumbing, and
- was around even in the initial commit (it literally went only through some 20 revisions as `cat-file.c`, was renamed to `builtin/cat-file.c` when made a builtin, and then saw less than 10 versions).

So, look into `builtin/cat-file.c`, search for `cmd_cat_file()` and look what it does.

            git_config(git_default_config);
            if (argc != 3)
                    usage("git cat-file [-t|-s|-e|-p|<type>] <sha1>");
            if (get_sha1(argv[2], sha1))
                    die("Not a valid object name %s", argv[2]);

Let’s skip over the obvious details; the only really interesting part here is the call to `get_sha1()`. It tries to interpret `argv[2]` as an object name, and if it refers to an object which is present in the current repository, it writes the resulting SHA-1 into the variable `sha1`.

Two things are interesting here:

- `get_sha1()` returns 0 on <span class="emphasis">_success_</span>. This might surprise some new Git hackers, but there is a long tradition in UNIX to return different negative numbers in case of different errors—​and 0 on success.
- the variable `sha1` in the function signature of `get_sha1()` is `unsigned char *`, but is actually expected to be a pointer to `unsigned char[20]`. This variable will contain the 160-bit SHA-1 of the given commit. Note that whenever a SHA-1 is passed as `unsigned char *`, it is the binary representation, as opposed to the ASCII representation in hex characters, which is passed as `char *`.

You will see both of these things throughout the code.

Now, for the meat:

            case 0:
                    buf = read_object_with_reference(sha1, argv[1], &size, NULL);

This is how you read a blob (actually, not only a blob, but any type of object). To know how the function `read_object_with_reference()` actually works, find the source code for it (something like `git grep read_object_with | grep ":[a-z]"` in the Git repository), and read the source.

To find out how the result can be used, just read on in `cmd_cat_file()`:

            write_or_die(1, buf, size);

Sometimes, you do not know where to look for a feature. In many such cases, it helps to search through the output of `git log`, and then `git show` the corresponding commit.

Example: If you know that there was some test case for `git bundle`, but do not remember where it was (yes, you <span class="emphasis">_could_</span> `git grep bundle t/`, but that does not illustrate the point!):

    $ git log --no-merges t/

In the pager (`less`), just search for "bundle", go a few lines back, and see that it is in commit 18449ab0. Now just copy this object name, and paste it into the command line

    $ git show 18449ab0

Voila.

Another example: Find out what to do in order to make some script a builtin:

    $ git log --no-merges --diff-filter=A builtin/*.c

You see, Git is actually the best tool to find out about the source of Git itself!

**Table of Contents**

<span class="section">[Git explained](#git-explained)</span>

## <span id="git-explained"></span>Git explained

<span class="term"><span id="def_alternate_object_database"></span>alternate object database</span>  
Via the alternates mechanism, a <a href="#def_repository" class="link">repository</a> can inherit part of its <a href="#def_object_database" class="link">object database</a> from another object database, which is called an "alternate".

<span class="term"><span id="def_bare_repository"></span>bare repository</span>  
A bare repository is normally an appropriately named <a href="#def_directory" class="link">directory</a> with a `.git` suffix that does not have a locally checked-out copy of any of the files under revision control. That is, all of the Git administrative and control files that would normally be present in the hidden `.git` sub-directory are directly present in the `repository.git` directory instead, and no other files are present and checked out. Usually publishers of public repositories make bare repositories available.

<span class="term"><span id="def_blob_object"></span>blob object</span>  
Untyped <a href="#def_object" class="link">object</a>, e.g. the contents of a file.

<span class="term"><span id="def_branch"></span>branch</span>  
A "branch" is a line of development. The most recent <a href="#def_commit" class="link">commit</a> on a branch is referred to as the tip of that branch. The tip of the branch is referenced by a branch <a href="#def_head" class="link">head</a>, which moves forward as additional development is done on the branch. A single Git <a href="#def_repository" class="link">repository</a> can track an arbitrary number of branches, but your <a href="#def_working_tree" class="link">working tree</a> is associated with just one of them (the "current" or "checked out" branch), and <a href="#def_HEAD" class="link">HEAD</a> points to that branch.

<span class="term"><span id="def_cache"></span>cache</span>  
Obsolete for: <a href="#def_index" class="link">index</a>.

<span class="term"><span id="def_chain"></span>chain</span>  
A list of objects, where each <a href="#def_object" class="link">object</a> in the list contains a reference to its successor (for example, the successor of a <a href="#def_commit" class="link">commit</a> could be one of its <a href="#def_parent" class="link">parents</a>).

<span class="term"><span id="def_changeset"></span>changeset</span>  
BitKeeper/cvsps speak for "<a href="#def_commit" class="link">commit</a>". Since Git does not store changes, but states, it really does not make sense to use the term "changesets" with Git.

<span class="term"><span id="def_checkout"></span>checkout</span>  
The action of updating all or part of the <a href="#def_working_tree" class="link">working tree</a> with a <a href="#def_tree_object" class="link">tree object</a> or <a href="#def_blob_object" class="link">blob</a> from the <a href="#def_object_database" class="link">object database</a>, and updating the <a href="#def_index" class="link">index</a> and <a href="#def_HEAD" class="link">HEAD</a> if the whole working tree has been pointed at a new <a href="#def_branch" class="link">branch</a>.

<span class="term"><span id="def_cherry-picking"></span>cherry-picking</span>  
In <a href="#def_SCM" class="link">SCM</a> jargon, "cherry pick" means to choose a subset of changes out of a series of changes (typically commits) and record them as a new series of changes on top of a different codebase. In Git, this is performed by the "git cherry-pick" command to extract the change introduced by an existing <a href="#def_commit" class="link">commit</a> and to record it based on the tip of the current <a href="#def_branch" class="link">branch</a> as a new commit.

<span class="term"><span id="def_clean"></span>clean</span>  
A <a href="#def_working_tree" class="link">working tree</a> is clean, if it corresponds to the <a href="#def_revision" class="link">revision</a> referenced by the current <a href="#def_head" class="link">head</a>. Also see "<a href="#def_dirty" class="link">dirty</a>".

<span class="term"><span id="def_commit"></span>commit</span>  
As a noun: A single point in the Git history; the entire history of a project is represented as a set of interrelated commits. The word "commit" is often used by Git in the same places other revision control systems use the words "revision" or "version". Also used as a short hand for <a href="#def_commit_object" class="link">commit object</a>.

As a verb: The action of storing a new snapshot of the project’s state in the Git history, by creating a new commit representing the current state of the <a href="#def_index" class="link">index</a> and advancing <a href="#def_HEAD" class="link">HEAD</a> to point at the new commit.

<span class="term"><span id="def_commit_object"></span>commit object</span>  
An <a href="#def_object" class="link">object</a> which contains the information about a particular <a href="#def_revision" class="link">revision</a>, such as <a href="#def_parent" class="link">parents</a>, committer, author, date and the <a href="#def_tree_object" class="link">tree object</a> which corresponds to the top <a href="#def_directory" class="link">directory</a> of the stored revision.

<span class="term"><span id="def_commit-ish"></span>commit-ish (also committish)</span>  
A <a href="#def_commit_object" class="link">commit object</a> or an <a href="#def_object" class="link">object</a> that can be recursively dereferenced to a commit object. The following are all commit-ishes: a commit object, a <a href="#def_tag_object" class="link">tag object</a> that points to a commit object, a tag object that points to a tag object that points to a commit object, etc.

<span class="term"><span id="def_core_git"></span>core Git</span>  
Fundamental data structures and utilities of Git. Exposes only limited source code management tools.

<span class="term"><span id="def_DAG"></span>DAG</span>  
Directed acyclic graph. The <a href="#def_commit_object" class="link">commit objects</a> form a directed acyclic graph, because they have parents (directed), and the graph of commit objects is acyclic (there is no <a href="#def_chain" class="link">chain</a> which begins and ends with the same <a href="#def_object" class="link">object</a>).

<span class="term"><span id="def_dangling_object"></span>dangling object</span>  
An <a href="#def_unreachable_object" class="link">unreachable object</a> which is not <a href="#def_reachable" class="link">reachable</a> even from other unreachable objects; a dangling object has no references to it from any reference or <a href="#def_object" class="link">object</a> in the <a href="#def_repository" class="link">repository</a>.

<span class="term"><span id="def_detached_HEAD"></span>detached HEAD</span>  
Normally the <a href="#def_HEAD" class="link">HEAD</a> stores the name of a <a href="#def_branch" class="link">branch</a>, and commands that operate on the history HEAD represents operate on the history leading to the tip of the branch the HEAD points at. However, Git also allows you to <a href="#def_checkout" class="link">check out</a> an arbitrary <a href="#def_commit" class="link">commit</a> that isn’t necessarily the tip of any particular branch. The HEAD in such a state is called "detached".

Note that commands that operate on the history of the current branch (e.g. `git commit` to build a new history on top of it) still work while the HEAD is detached. They update the HEAD to point at the tip of the updated history without affecting any branch. Commands that update or inquire information <span class="emphasis">_about_</span> the current branch (e.g. `git branch --set-upstream-to` that sets what remote-tracking branch the current branch integrates with) obviously do not work, as there is no (real) current branch to ask about in this state.

<span class="term"><span id="def_directory"></span>directory</span>  
The list you get with "ls" :-)

<span class="term"><span id="def_dirty"></span>dirty</span>  
A <a href="#def_working_tree" class="link">working tree</a> is said to be "dirty" if it contains modifications which have not been <a href="#def_commit" class="link">committed</a> to the current <a href="#def_branch" class="link">branch</a>.

<span class="term"><span id="def_evil_merge"></span>evil merge</span>  
An evil merge is a <a href="#def_merge" class="link">merge</a> that introduces changes that do not appear in any <a href="#def_parent" class="link">parent</a>.

<span class="term"><span id="def_fast_forward"></span>fast-forward</span>  
A fast-forward is a special type of <a href="#def_merge" class="link">merge</a> where you have a <a href="#def_revision" class="link">revision</a> and you are "merging" another <a href="#def_branch" class="link">branch</a>'s changes that happen to be a descendant of what you have. In such a case, you do not make a new <a href="#def_merge" class="link">merge</a> <a href="#def_commit" class="link">commit</a> but instead just update to his revision. This will happen frequently on a <a href="#def_remote_tracking_branch" class="link">remote-tracking branch</a> of a remote <a href="#def_repository" class="link">repository</a>.

<span class="term"><span id="def_fetch"></span>fetch</span>  
Fetching a <a href="#def_branch" class="link">branch</a> means to get the branch’s <a href="#def_head_ref" class="link">head ref</a> from a remote <a href="#def_repository" class="link">repository</a>, to find out which objects are missing from the local <a href="#def_object_database" class="link">object database</a>, and to get them, too. See also <a href="git-fetch.html" class="ulink">git-fetch(1)</a>.

<span class="term"><span id="def_file_system"></span>file system</span>  
Linus Torvalds originally designed Git to be a user space file system, i.e. the infrastructure to hold files and directories. That ensured the efficiency and speed of Git.

<span class="term"><span id="def_git_archive"></span>Git archive</span>  
Synonym for <a href="#def_repository" class="link">repository</a> (for arch people).

<span class="term"><span id="def_gitfile"></span>gitfile</span>  
A plain file `.git` at the root of a working tree that points at the directory that is the real repository.

<span class="term"><span id="def_grafts"></span>grafts</span>  
Grafts enables two otherwise different lines of development to be joined together by recording fake ancestry information for commits. This way you can make Git pretend the set of <a href="#def_parent" class="link">parents</a> a <a href="#def_commit" class="link">commit</a> has is different from what was recorded when the commit was created. Configured via the `.git/info/grafts` file.

Note that the grafts mechanism is outdated and can lead to problems transferring objects between repositories; see <a href="git-replace.html" class="ulink">git-replace(1)</a> for a more flexible and robust system to do the same thing.

<span class="term"><span id="def_hash"></span>hash</span>  
In Git’s context, synonym for <a href="#def_object_name" class="link">object name</a>.

<span class="term"><span id="def_head"></span>head</span>  
A <a href="#def_ref" class="link">named reference</a> to the <a href="#def_commit" class="link">commit</a> at the tip of a <a href="#def_branch" class="link">branch</a>. Heads are stored in a file in `$GIT_DIR/refs/heads/` directory, except when using packed refs. (See <a href="git-pack-refs.html" class="ulink">git-pack-refs(1)</a>.)

<span class="term"><span id="def_HEAD"></span>HEAD</span>  
The current <a href="#def_branch" class="link">branch</a>. In more detail: Your <a href="#def_working_tree" class="link">working tree</a> is normally derived from the state of the tree referred to by HEAD. HEAD is a reference to one of the <a href="#def_head" class="link">heads</a> in your repository, except when using a <a href="#def_detached_HEAD" class="link">detached HEAD</a>, in which case it directly references an arbitrary commit.

<span class="term"><span id="def_head_ref"></span>head ref</span>  
A synonym for <a href="#def_head" class="link">head</a>.

<span class="term"><span id="def_hook"></span>hook</span>  
During the normal execution of several Git commands, call-outs are made to optional scripts that allow a developer to add functionality or checking. Typically, the hooks allow for a command to be pre-verified and potentially aborted, and allow for a post-notification after the operation is done. The hook scripts are found in the `$GIT_DIR/hooks/` directory, and are enabled by simply removing the `.sample` suffix from the filename. In earlier versions of Git you had to make them executable.

<span class="term"><span id="def_index"></span>index</span>  
A collection of files with stat information, whose contents are stored as objects. The index is a stored version of your <a href="#def_working_tree" class="link">working tree</a>. Truth be told, it can also contain a second, and even a third version of a working tree, which are used when <a href="#def_merge" class="link">merging</a>.

<span class="term"><span id="def_index_entry"></span>index entry</span>  
The information regarding a particular file, stored in the <a href="#def_index" class="link">index</a>. An index entry can be unmerged, if a <a href="#def_merge" class="link">merge</a> was started, but not yet finished (i.e. if the index contains multiple versions of that file).

<span class="term"><span id="def_master"></span>master</span>  
The default development <a href="#def_branch" class="link">branch</a>. Whenever you create a Git <a href="#def_repository" class="link">repository</a>, a branch named "master" is created, and becomes the active branch. In most cases, this contains the local development, though that is purely by convention and is not required.

<span class="term"><span id="def_merge"></span>merge</span>  
As a verb: To bring the contents of another <a href="#def_branch" class="link">branch</a> (possibly from an external <a href="#def_repository" class="link">repository</a>) into the current branch. In the case where the merged-in branch is from a different repository, this is done by first <a href="#def_fetch" class="link">fetching</a> the remote branch and then merging the result into the current branch. This combination of fetch and merge operations is called a <a href="#def_pull" class="link">pull</a>. Merging is performed by an automatic process that identifies changes made since the branches diverged, and then applies all those changes together. In cases where changes conflict, manual intervention may be required to complete the merge.

As a noun: unless it is a <a href="#def_fast_forward" class="link">fast-forward</a>, a successful merge results in the creation of a new <a href="#def_commit" class="link">commit</a> representing the result of the merge, and having as <a href="#def_parent" class="link">parents</a> the tips of the merged <a href="#def_branch" class="link">branches</a>. This commit is referred to as a "merge commit", or sometimes just a "merge".

<span class="term"><span id="def_object"></span>object</span>  
The unit of storage in Git. It is uniquely identified by the <a href="#def_SHA1" class="link">SHA-1</a> of its contents. Consequently, an object cannot be changed.

<span class="term"><span id="def_object_database"></span>object database</span>  
Stores a set of "objects", and an individual <a href="#def_object" class="link">object</a> is identified by its <a href="#def_object_name" class="link">object name</a>. The objects usually live in `$GIT_DIR/objects/`.

<span class="term"><span id="def_object_identifier"></span>object identifier</span>  
Synonym for <a href="#def_object_name" class="link">object name</a>.

<span class="term"><span id="def_object_name"></span>object name</span>  
The unique identifier of an <a href="#def_object" class="link">object</a>. The object name is usually represented by a 40 character hexadecimal string. Also colloquially called <a href="#def_SHA1" class="link">SHA-1</a>.

<span class="term"><span id="def_object_type"></span>object type</span>  
One of the identifiers "<a href="#def_commit_object" class="link">commit</a>", "<a href="#def_tree_object" class="link">tree</a>", "<a href="#def_tag_object" class="link">tag</a>" or "<a href="#def_blob_object" class="link">blob</a>" describing the type of an <a href="#def_object" class="link">object</a>.

<span class="term"><span id="def_octopus"></span>octopus</span>  
To <a href="#def_merge" class="link">merge</a> more than two <a href="#def_branch" class="link">branches</a>.

<span class="term"><span id="def_origin"></span>origin</span>  
The default upstream <a href="#def_repository" class="link">repository</a>. Most projects have at least one upstream project which they track. By default <span class="emphasis">_origin_</span> is used for that purpose. New upstream updates will be fetched into <a href="#def_remote_tracking_branch" class="link">remote-tracking branches</a> named origin/name-of-upstream-branch, which you can see using `git branch -r`.

<span class="term"><span id="def_overlay"></span>overlay</span>  
Only update and add files to the working directory, but don’t delete them, similar to how <span class="emphasis">_cp -R_</span> would update the contents in the destination directory. This is the default mode in a <a href="#def_checkout" class="link">checkout</a> when checking out files from the <a href="#def_index" class="link">index</a> or a <a href="#def_tree-ish" class="link">tree-ish</a>. In contrast, no-overlay mode also deletes tracked files not present in the source, similar to <span class="emphasis">_rsync --delete_</span>.

<span class="term"><span id="def_pack"></span>pack</span>  
A set of objects which have been compressed into one file (to save space or to transmit them efficiently).

<span class="term"><span id="def_pack_index"></span>pack index</span>  
The list of identifiers, and other information, of the objects in a <a href="#def_pack" class="link">pack</a>, to assist in efficiently accessing the contents of a pack.

<span class="term"><span id="def_pathspec"></span>pathspec</span>  
Pattern used to limit paths in Git commands.

Pathspecs are used on the command line of "git ls-files", "git ls-tree", "git add", "git grep", "git diff", "git checkout", and many other commands to limit the scope of operations to some subset of the tree or worktree. See the documentation of each command for whether paths are relative to the current directory or toplevel. The pathspec syntax is as follows:

- any path matches itself
- the pathspec up to the last slash represents a directory prefix. The scope of that pathspec is limited to that subtree.
- the rest of the pathspec is a pattern for the remainder of the pathname. Paths relative to the directory prefix will be matched against that pattern using fnmatch(3); in particular, <span class="emphasis">\*\*_</span> and <span class="emphasis">_?*</span> <span class="emphasis">*can\*</span> match directory separators.

For example, Documentation/\*.jpg will match all .jpg files in the Documentation subtree, including Documentation/chapter_1/figure_1.jpg.

A pathspec that begins with a colon `:` has special meaning. In the short form, the leading colon `:` is followed by zero or more "magic signature" letters (which optionally is terminated by another colon `:`), and the remainder is the pattern to match against the path. The "magic signature" consists of ASCII symbols that are neither alphanumeric, glob, regex special characters nor colon. The optional colon that terminates the "magic signature" can be omitted if the pattern begins with a character that does not belong to "magic signature" symbol set and is not a colon.

In the long form, the leading colon `:` is followed by an open parenthesis `(`, a comma-separated list of zero or more "magic words", and a close parentheses `)`, and the remainder is the pattern to match against the path.

A pathspec with only a colon means "there is no pathspec". This form should not be combined with other pathspec.

<span class="term">top</span>  
The magic word `top` (magic signature: `/`) makes the pattern match from the root of the working tree, even when you are running the command from inside a subdirectory.

<span class="term">literal</span>  
Wildcards in the pattern such as `*` or `?` are treated as literal characters.

<span class="term">icase</span>  
Case insensitive match.

<span class="term">glob</span>  
Git treats the pattern as a shell glob suitable for consumption by fnmatch(3) with the FNM_PATHNAME flag: wildcards in the pattern will not match a / in the pathname. For example, "Documentation/\*.html" matches "Documentation/git.html" but not "Documentation/ppc/ppc.html" or "tools/perf/Documentation/perf.html".

Two consecutive asterisks ("`**`") in patterns matched against full pathname may have special meaning:

- A leading "`**`" followed by a slash means match in all directories. For example, "`**/foo`" matches file or directory "`foo`" anywhere, the same as pattern "`foo`". "`**/foo/bar`" matches file or directory "`bar`" anywhere that is directly under directory "`foo`".
- A trailing "`/**`" matches everything inside. For example, "`abc/**`" matches all files inside directory "abc", relative to the location of the `.gitignore` file, with infinite depth.
- A slash followed by two consecutive asterisks then a slash matches zero or more directories. For example, "`a/**/b`" matches "`a/b`", "`a/x/b`", "`a/x/y/b`" and so on.
- Other consecutive asterisks are considered invalid.

  Glob magic is incompatible with literal magic.

<span class="term">attr</span>  
After `attr:` comes a space separated list of "attribute requirements", all of which must be met in order for the path to be considered a match; this is in addition to the usual non-magic pathspec pattern matching. See <a href="gitattributes.html" class="ulink">gitattributes(5)</a>.

Each of the attribute requirements for the path takes one of these forms:

- "`ATTR`" requires that the attribute `ATTR` be set.
- "`-ATTR`" requires that the attribute `ATTR` be unset.
- "`ATTR=VALUE`" requires that the attribute `ATTR` be set to the string `VALUE`.
- "`!ATTR`" requires that the attribute `ATTR` be unspecified.

  Note that when matching against a tree object, attributes are still obtained from working tree, not from the given tree object.

<span class="term">exclude</span>  
After a path matches any non-exclude pathspec, it will be run through all exclude pathspecs (magic signature: `!` or its synonym `^`). If it matches, the path is ignored. When there is no non-exclude pathspec, the exclusion is applied to the result set as if invoked without any pathspec.

<span class="term"><span id="def_parent"></span>parent</span>  
A <a href="#def_commit_object" class="link">commit object</a> contains a (possibly empty) list of the logical predecessor(s) in the line of development, i.e. its parents.

<span class="term"><span id="def_pickaxe"></span>pickaxe</span>  
The term <a href="#def_pickaxe" class="link">pickaxe</a> refers to an option to the diffcore routines that help select changes that add or delete a given text string. With the `--pickaxe-all` option, it can be used to view the full <a href="#def_changeset" class="link">changeset</a> that introduced or removed, say, a particular line of text. See <a href="git-diff.html" class="ulink">git-diff(1)</a>.

<span class="term"><span id="def_plumbing"></span>plumbing</span>  
Cute name for <a href="#def_core_git" class="link">core Git</a>.

<span class="term"><span id="def_porcelain"></span>porcelain</span>  
Cute name for programs and program suites depending on <a href="#def_core_git" class="link">core Git</a>, presenting a high level access to core Git. Porcelains expose more of a <a href="#def_SCM" class="link">SCM</a> interface than the <a href="#def_plumbing" class="link">plumbing</a>.

<span class="term"><span id="def_per_worktree_ref"></span>per-worktree ref</span>  
Refs that are per-<a href="#def_working_tree" class="link">worktree</a>, rather than global. This is presently only <a href="#def_HEAD" class="link">HEAD</a> and any refs that start with `refs/bisect/`, but might later include other unusual refs.

<span class="term"><span id="def_pseudoref"></span>pseudoref</span>  
Pseudorefs are a class of files under `$GIT_DIR` which behave like refs for the purposes of rev-parse, but which are treated specially by git. Pseudorefs both have names that are all-caps, and always start with a line consisting of a <a href="#def_SHA1" class="link">SHA-1</a> followed by whitespace. So, HEAD is not a pseudoref, because it is sometimes a symbolic ref. They might optionally contain some additional data. `MERGE_HEAD` and `CHERRY_PICK_HEAD` are examples. Unlike <a href="#def_per_worktree_ref" class="link">per-worktree refs</a>, these files cannot be symbolic refs, and never have reflogs. They also cannot be updated through the normal ref update machinery. Instead, they are updated by directly writing to the files. However, they can be read as if they were refs, so `git rev-parse MERGE_HEAD` will work.

<span class="term"><span id="def_pull"></span>pull</span>  
Pulling a <a href="#def_branch" class="link">branch</a> means to <a href="#def_fetch" class="link">fetch</a> it and <a href="#def_merge" class="link">merge</a> it. See also <a href="git-pull.html" class="ulink">git-pull(1)</a>.

<span class="term"><span id="def_push"></span>push</span>  
Pushing a <a href="#def_branch" class="link">branch</a> means to get the branch’s <a href="#def_head_ref" class="link">head ref</a> from a remote <a href="#def_repository" class="link">repository</a>, find out if it is an ancestor to the branch’s local head ref, and in that case, putting all objects, which are <a href="#def_reachable" class="link">reachable</a> from the local head ref, and which are missing from the remote repository, into the remote <a href="#def_object_database" class="link">object database</a>, and updating the remote head ref. If the remote <a href="#def_head" class="link">head</a> is not an ancestor to the local head, the push fails.

<span class="term"><span id="def_reachable"></span>reachable</span>  
All of the ancestors of a given <a href="#def_commit" class="link">commit</a> are said to be "reachable" from that commit. More generally, one <a href="#def_object" class="link">object</a> is reachable from another if we can reach the one from the other by a <a href="#def_chain" class="link">chain</a> that follows <a href="#def_tag" class="link">tags</a> to whatever they tag, <a href="#def_commit_object" class="link">commits</a> to their parents or trees, and <a href="#def_tree_object" class="link">trees</a> to the trees or <a href="#def_blob_object" class="link">blobs</a> that they contain.

<span class="term"><span id="def_rebase"></span>rebase</span>  
To reapply a series of changes from a <a href="#def_branch" class="link">branch</a> to a different base, and reset the <a href="#def_head" class="link">head</a> of that branch to the result.

<span class="term"><span id="def_ref"></span>ref</span>  
A name that begins with `refs/` (e.g. `refs/heads/master`) that points to an <a href="#def_object_name" class="link">object name</a> or another ref (the latter is called a <a href="#def_symref" class="link">symbolic ref</a>). For convenience, a ref can sometimes be abbreviated when used as an argument to a Git command; see <a href="gitrevisions.html" class="ulink">gitrevisions(7)</a> for details. Refs are stored in the <a href="#def_repository" class="link">repository</a>.

The ref namespace is hierarchical. Different subhierarchies are used for different purposes (e.g. the `refs/heads/` hierarchy is used to represent local branches).

There are a few special-purpose refs that do not begin with `refs/`. The most notable example is `HEAD`.

<span class="term"><span id="def_reflog"></span>reflog</span>  
A reflog shows the local "history" of a ref. In other words, it can tell you what the 3rd last revision in <span class="emphasis">_this_</span> repository was, and what was the current state in <span class="emphasis">_this_</span> repository, yesterday 9:14pm. See <a href="git-reflog.html" class="ulink">git-reflog(1)</a> for details.

<span class="term"><span id="def_refspec"></span>refspec</span>  
A "refspec" is used by <a href="#def_fetch" class="link">fetch</a> and <a href="#def_push" class="link">push</a> to describe the mapping between remote <a href="#def_ref" class="link">ref</a> and local ref.

<span class="term"><span id="def_remote"></span>remote repository</span>  
A <a href="#def_repository" class="link">repository</a> which is used to track the same project but resides somewhere else. To communicate with remotes, see <a href="#def_fetch" class="link">fetch</a> or <a href="#def_push" class="link">push</a>.

<span class="term"><span id="def_remote_tracking_branch"></span>remote-tracking branch</span>  
A <a href="#def_ref" class="link">ref</a> that is used to follow changes from another <a href="#def_repository" class="link">repository</a>. It typically looks like <span class="emphasis">_refs/remotes/foo/bar_</span> (indicating that it tracks a branch named <span class="emphasis">_bar_</span> in a remote named <span class="emphasis">_foo_</span>), and matches the right-hand-side of a configured fetch <a href="#def_refspec" class="link">refspec</a>. A remote-tracking branch should not contain direct modifications or have local commits made to it.

<span class="term"><span id="def_repository"></span>repository</span>  
A collection of <a href="#def_ref" class="link">refs</a> together with an <a href="#def_object_database" class="link">object database</a> containing all objects which are <a href="#def_reachable" class="link">reachable</a> from the refs, possibly accompanied by meta data from one or more <a href="#def_porcelain" class="link">porcelains</a>. A repository can share an object database with other repositories via <a href="#def_alternate_object_database" class="link">alternates mechanism</a>.

<span class="term"><span id="def_resolve"></span>resolve</span>  
The action of fixing up manually what a failed automatic <a href="#def_merge" class="link">merge</a> left behind.

<span class="term"><span id="def_revision"></span>revision</span>  
Synonym for <a href="#def_commit" class="link">commit</a> (the noun).

<span class="term"><span id="def_rewind"></span>rewind</span>  
To throw away part of the development, i.e. to assign the <a href="#def_head" class="link">head</a> to an earlier <a href="#def_revision" class="link">revision</a>.

<span class="term"><span id="def_SCM"></span>SCM</span>  
Source code management (tool).

<span class="term"><span id="def_SHA1"></span>SHA-1</span>  
"Secure Hash Algorithm 1"; a cryptographic hash function. In the context of Git used as a synonym for <a href="#def_object_name" class="link">object name</a>.

<span class="term"><span id="def_shallow_clone"></span>shallow clone</span>  
Mostly a synonym to <a href="#def_shallow_repository" class="link">shallow repository</a> but the phrase makes it more explicit that it was created by running `git clone --depth=...` command.

<span class="term"><span id="def_shallow_repository"></span>shallow repository</span>  
A shallow <a href="#def_repository" class="link">repository</a> has an incomplete history some of whose <a href="#def_commit" class="link">commits</a> have <a href="#def_parent" class="link">parents</a> cauterized away (in other words, Git is told to pretend that these commits do not have the parents, even though they are recorded in the <a href="#def_commit_object" class="link">commit object</a>). This is sometimes useful when you are interested only in the recent history of a project even though the real history recorded in the upstream is much larger. A shallow repository is created by giving the `--depth` option to <a href="git-clone.html" class="ulink">git-clone(1)</a>, and its history can be later deepened with <a href="git-fetch.html" class="ulink">git-fetch(1)</a>.

<span class="term"><span id="def_stash"></span>stash entry</span>  
An <a href="#def_object" class="link">object</a> used to temporarily store the contents of a <a href="#def_dirty" class="link">dirty</a> working directory and the index for future reuse.

<span class="term"><span id="def_submodule"></span>submodule</span>  
A <a href="#def_repository" class="link">repository</a> that holds the history of a separate project inside another repository (the latter of which is called <a href="#def_superproject" class="link">superproject</a>).

<span class="term"><span id="def_superproject"></span>superproject</span>  
A <a href="#def_repository" class="link">repository</a> that references repositories of other projects in its working tree as <a href="#def_submodule" class="link">submodules</a>. The superproject knows about the names of (but does not hold copies of) commit objects of the contained submodules.

<span class="term"><span id="def_symref"></span>symref</span>  
Symbolic reference: instead of containing the <a href="#def_SHA1" class="link">SHA-1</a> id itself, it is of the format <span class="emphasis">_ref: refs/some/thing_</span> and when referenced, it recursively dereferences to this reference. <span class="emphasis">_<a href="#def_HEAD" class="link">HEAD</a>_</span> is a prime example of a symref. Symbolic references are manipulated with the <a href="git-symbolic-ref.html" class="ulink">git-symbolic-ref(1)</a> command.

<span class="term"><span id="def_tag"></span>tag</span>  
A <a href="#def_ref" class="link">ref</a> under `refs/tags/` namespace that points to an object of an arbitrary type (typically a tag points to either a <a href="#def_tag_object" class="link">tag</a> or a <a href="#def_commit_object" class="link">commit object</a>). In contrast to a <a href="#def_head" class="link">head</a>, a tag is not updated by the `commit` command. A Git tag has nothing to do with a Lisp tag (which would be called an <a href="#def_object_type" class="link">object type</a> in Git’s context). A tag is most typically used to mark a particular point in the commit ancestry <a href="#def_chain" class="link">chain</a>.

<span class="term"><span id="def_tag_object"></span>tag object</span>  
An <a href="#def_object" class="link">object</a> containing a <a href="#def_ref" class="link">ref</a> pointing to another object, which can contain a message just like a <a href="#def_commit_object" class="link">commit object</a>. It can also contain a (PGP) signature, in which case it is called a "signed tag object".

<span class="term"><span id="def_topic_branch"></span>topic branch</span>  
A regular Git <a href="#def_branch" class="link">branch</a> that is used by a developer to identify a conceptual line of development. Since branches are very easy and inexpensive, it is often desirable to have several small branches that each contain very well defined concepts or small incremental yet related changes.

<span class="term"><span id="def_tree"></span>tree</span>  
Either a <a href="#def_working_tree" class="link">working tree</a>, or a <a href="#def_tree_object" class="link">tree object</a> together with the dependent <a href="#def_blob_object" class="link">blob</a> and tree objects (i.e. a stored representation of a working tree).

<span class="term"><span id="def_tree_object"></span>tree object</span>  
An <a href="#def_object" class="link">object</a> containing a list of file names and modes along with refs to the associated blob and/or tree objects. A <a href="#def_tree" class="link">tree</a> is equivalent to a <a href="#def_directory" class="link">directory</a>.

<span class="term"><span id="def_tree-ish"></span>tree-ish (also treeish)</span>  
A <a href="#def_tree_object" class="link">tree object</a> or an <a href="#def_object" class="link">object</a> that can be recursively dereferenced to a tree object. Dereferencing a <a href="#def_commit_object" class="link">commit object</a> yields the tree object corresponding to the <a href="#def_revision" class="link">revision</a>'s top <a href="#def_directory" class="link">directory</a>. The following are all tree-ishes: a <a href="#def_commit-ish" class="link">commit-ish</a>, a tree object, a <a href="#def_tag_object" class="link">tag object</a> that points to a tree object, a tag object that points to a tag object that points to a tree object, etc.

<span class="term"><span id="def_unmerged_index"></span>unmerged index</span>  
An <a href="#def_index" class="link">index</a> which contains unmerged <a href="#def_index_entry" class="link">index entries</a>.

<span class="term"><span id="def_unreachable_object"></span>unreachable object</span>  
An <a href="#def_object" class="link">object</a> which is not <a href="#def_reachable" class="link">reachable</a> from a <a href="#def_branch" class="link">branch</a>, <a href="#def_tag" class="link">tag</a>, or any other reference.

<span class="term"><span id="def_upstream_branch"></span>upstream branch</span>  
The default <a href="#def_branch" class="link">branch</a> that is merged into the branch in question (or the branch in question is rebased onto). It is configured via branch.&lt;name&gt;.remote and branch.&lt;name&gt;.merge. If the upstream branch of <span class="emphasis">_A_</span> is <span class="emphasis">_origin/B_</span> sometimes we say "<span class="emphasis">_A_</span> is tracking <span class="emphasis">_origin/B_</span>".

<span class="term"><span id="def_working_tree"></span>working tree</span>  
The tree of actual checked out files. The working tree normally contains the contents of the <a href="#def_HEAD" class="link">HEAD</a> commit’s tree, plus any local changes that you have made but not yet committed.

**Table of Contents**

<span class="section">[Creating a new repository](#quick-creating-a-new-repository)</span>

<span class="section">[Managing branches](#managing-branches)</span>

<span class="section">[Exploring history](#exploring-history)</span>

<span class="section">[Making changes](#making-changes)</span>

<span class="section">[Merging](#merging)</span>

<span class="section">[Sharing your changes](#sharing-your-changes)</span>

<span class="section">[Repository maintenance](#repository-maintenance)</span>

This is a quick summary of the major commands; the previous chapters explain how these work in more detail.

## <span id="quick-creating-a-new-repository"></span>Creating a new repository

From a tarball:

    $ tar xzf project.tar.gz
    $ cd project
    $ git init
    Initialized empty Git repository in .git/
    $ git add .
    $ git commit

From a remote repository:

    $ git clone git://example.com/pub/project.git
    $ cd project

## <span id="managing-branches"></span>Managing branches

    $ git branch                    # list all local branches in this repo
    $ git switch test               # switch working directory to branch "test"
    $ git branch new                # create branch "new" starting at current HEAD
    $ git branch -d new             # delete branch "new"

Instead of basing a new branch on current HEAD (the default), use:

    $ git branch new test    # branch named "test"
    $ git branch new v2.6.15 # tag named v2.6.15
    $ git branch new HEAD^   # commit before the most recent
    $ git branch new HEAD^^  # commit before that
    $ git branch new test~10 # ten commits before tip of branch "test"

Create and switch to a new branch at the same time:

    $ git switch -c new v2.6.15

Update and examine branches from the repository you cloned from:

    $ git fetch             # update
    $ git branch -r         # list
      origin/master
      origin/next
      ...
    $ git switch -c masterwork origin/master

Fetch a branch from a different repository, and give it a new name in your repository:

    $ git fetch git://example.com/project.git theirbranch:mybranch
    $ git fetch git://example.com/project.git v2.6.15:mybranch

Keep a list of repositories you work with regularly:

    $ git remote add example git://example.com/project.git
    $ git remote                    # list remote repositories
    example
    origin
    $ git remote show example       # get details
    * remote example
      URL: git://example.com/project.git
      Tracked remote branches
        master
        next
        ...
    $ git fetch example             # update branches from example
    $ git branch -r                 # list all remote branches

## <span id="exploring-history"></span>Exploring history

    $ gitk                      # visualize and browse history
    $ git log                   # list all commits
    $ git log src/              # ...modifying src/
    $ git log v2.6.15..v2.6.16  # ...in v2.6.16, not in v2.6.15
    $ git log master..test      # ...in branch test, not in branch master
    $ git log test..master      # ...in branch master, but not in test
    $ git log test...master     # ...in one branch, not in both
    $ git log -S'foo()'         # ...where difference contain "foo()"
    $ git log --since="2 weeks ago"
    $ git log -p                # show patches as well
    $ git show                  # most recent commit
    $ git diff v2.6.15..v2.6.16 # diff between two tagged versions
    $ git diff v2.6.15..HEAD    # diff with current head
    $ git grep "foo()"          # search working directory for "foo()"
    $ git grep v2.6.15 "foo()"  # search old tree for "foo()"
    $ git show v2.6.15:a.txt    # look at old version of a.txt

Search for regressions:

    $ git bisect start
    $ git bisect bad                # current version is bad
    $ git bisect good v2.6.13-rc2   # last known good revision
    Bisecting: 675 revisions left to test after this
                                    # test here, then:
    $ git bisect good               # if this revision is good, or
    $ git bisect bad                # if this revision is bad.
                                    # repeat until done.

## <span id="making-changes"></span>Making changes

Make sure Git knows who to blame:

    $ cat >>~/.gitconfig <<\EOF
    [user]
            name = Your Name Comes Here
            email = you@yourdomain.example.com
    EOF

Select file contents to include in the next commit, then make the commit:

    $ git add a.txt    # updated file
    $ git add b.txt    # new file
    $ git rm c.txt     # old file
    $ git commit

Or, prepare and create the commit in one step:

    $ git commit d.txt # use latest content only of d.txt
    $ git commit -a    # use latest content of all tracked files

## <span id="merging"></span>Merging

    $ git merge test   # merge branch "test" into the current branch
    $ git pull git://example.com/project.git master
                       # fetch and merge in remote branch
    $ git pull . test  # equivalent to git merge test

## <span id="sharing-your-changes"></span>Sharing your changes

Importing or exporting patches:

    $ git format-patch origin..HEAD # format a patch for each commit
                                    # in HEAD but not in origin
    $ git am mbox # import patches from the mailbox "mbox"

Fetch a branch in a different Git repository, then merge into the current branch:

    $ git pull git://example.com/project.git theirbranch

Store the fetched branch into a local branch before merging into the current branch:

    $ git pull git://example.com/project.git theirbranch:mybranch

After creating commits on a local branch, update the remote branch with your commits:

    $ git push ssh://example.com/project.git mybranch:theirbranch

When remote and local branch are both named "test":

    $ git push ssh://example.com/project.git test

Shortcut version for a frequently used remote repository:

    $ git remote add example ssh://example.com/project.git
    $ git push example test

## <span id="repository-maintenance"></span>Repository maintenance

Check for corruption:

    $ git fsck

Recompress, remove unused cruft:

    $ git gc

**Table of Contents**

<span class="section">[Todo list](#todo-list)</span>

## <span id="todo-list"></span>Todo list

This is a work in progress.

The basic requirements:

- It must be readable in order, from beginning to end, by someone intelligent with a basic grasp of the UNIX command line, but without any special knowledge of Git. If necessary, any other prerequisites should be specifically mentioned as they arise.
- Whenever possible, section headings should clearly describe the task they explain how to do, in language that requires no more knowledge than necessary: for example, "importing patches into a project" rather than "the `git am` command"

Think about how to create a clear chapter dependency graph that will allow people to get to important topics without necessarily reading everything in between.

Scan `Documentation/` for other stuff left out; in particular:

- howto’s
- some of `technical/`?
- hooks
- list of commands in <a href="git.html" class="ulink">git(1)</a>

Scan email archives for other stuff left out

Scan man pages to see if any assume more background than this manual provides.

Add more good examples. Entire sections of just cookbook examples might be a good idea; maybe make an "advanced examples" section a standard end-of-chapter section?

Include cross-references to the glossary, where appropriate.

Add a section on working with other version control systems, including CVS, Subversion, and just imports of series of release tarballs.

Write a chapter on using plumbing and writing scripts.

Alternates, clone -reference, etc.

More on recovery from repository corruption. See: <a href="https://lore.kernel.org/git/Pine.LNX.4.64.0702272039540.12485@woody.linux-foundation.org/" class="ulink">https://lore.kernel.org/git/Pine.LNX.4.64.0702272039540.12485@woody.linux-foundation.org/</a> <a href="https://lore.kernel.org/git/Pine.LNX.4.64.0702141033400.3604@woody.linux-foundation.org/" class="ulink">https://lore.kernel.org/git/Pine.LNX.4.64.0702141033400.3604@woody.linux-foundation.org/</a>
