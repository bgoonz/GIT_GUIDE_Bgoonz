# gitcvs-migration(7) Manual Page

## NAME

gitcvs-migration - Git for CVS users

## SYNOPSIS

    git cvsimport *

## DESCRIPTION

Git differs from CVS in that every working tree contains a repository with a full copy of the project history, and no repository is inherently more important than any other. However, you can emulate the CVS model by designating a single shared repository which people can synchronize with; this document explains how to do that.

Some basic familiarity with Git is required. Having gone through [gittutorial(7)](gittutorial.html) and [gitglossary(7)](gitglossary.html) should be sufficient.

## Developing against a shared repository

Suppose a shared repository is set up in /pub/repo.git on the host foo.com. Then as an individual committer you can clone the shared repository over ssh with:

    $ git clone foo.com:/pub/repo.git/ my-project
    $ cd my-project

and hack away. The equivalent of _cvs update_ is

    $ git pull origin

which merges in any work that others might have done since the clone operation. If there are uncommitted changes in your working tree, commit them first before running git pull.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><div class="title">Note</div></td><td><div class="paragraph"><p>The <em>pull</em> command knows where to get updates from because of certain configuration variables that were set by the first <em>git clone</em> command; see <code>git config -l</code> and the <a href="git-config.html">git-config(1)</a> man page for details.</p></div></td></tr></tbody></table>

You can update the shared repository with your changes by first committing your changes, and then using the _git push_ command:

    $ git push origin master

to "push" those commits to the shared repository. If someone else has updated the repository more recently, _git push_, like _cvs commit_, will complain, in which case you must pull any changes before attempting the push again.

In the _git push_ command above we specify the name of the remote branch to update (`master`). If we leave that out, _git push_ tries to update any branches in the remote repository that have the same name as a branch in the local repository. So the last _push_ can be done with either of:

    $ git push origin
    $ git push foo.com:/pub/project.git/

as long as the shared repository does not have any branches other than `master`.

## Setting Up a Shared Repository

We assume you have already created a Git repository for your project, possibly created from scratch or from a tarball (see [gittutorial(7)](gittutorial.html)), or imported from an already existing CVS repository (see the next section).

Assume your existing repo is at /home/alice/myproject. Create a new "bare" repository (a repository without a working tree) and fetch your project into it:

    $ mkdir /pub/my-repo.git
    $ cd /pub/my-repo.git
    $ git --bare init --shared
    $ git --bare fetch /home/alice/myproject master:master

Next, give every team member read/write access to this repository. One easy way to do this is to give all the team members ssh access to the machine where the repository is hosted. If you don’t want to give them a full shell on the machine, there is a restricted shell which only allows users to do Git pushes and pulls; see [git-shell(1)](git-shell.html).

Put all the committers in the same group, and make the repository writable by that group:

    $ chgrp -R $group /pub/my-repo.git

Make sure committers have a umask of at most 027, so that the directories they create are writable and searchable by other group members.

## Importing a CVS archive

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><div class="title">Note</div></td><td>These instructions use the <code>git-cvsimport</code> script which ships with git, but other importers may provide better results. See the note in <a href="git-cvsimport.html">git-cvsimport(1)</a> for other options.</td></tr></tbody></table>

First, install version 2.1 or higher of cvsps from <https://github.com/andreyvit/cvsps> and make sure it is in your path. Then cd to a checked out CVS working directory of the project you are interested in and run [git-cvsimport(1)](git-cvsimport.html):

    $ git cvsimport -C <destination> <module>

This puts a Git archive of the named CVS module in the directory &lt;destination&gt;, which will be created if necessary.

The import checks out from CVS every revision of every file. Reportedly cvsimport can average some twenty revisions per second, so for a medium-sized project this should not take more than a couple of minutes. Larger projects or remote repositories may take longer.

The main trunk is stored in the Git branch named `origin`, and additional CVS branches are stored in Git branches with the same names. The most recent version of the main trunk is also left checked out on the `master` branch, so you can start adding your own changes right away.

The import is incremental, so if you call it again next month it will fetch any CVS updates that have been made in the meantime. For this to work, you must not modify the imported branches; instead, create new branches for your own changes, and merge in the imported branches as necessary.

If you want a shared repository, you will need to make a bare clone of the imported directory, as described above. Then treat the imported directory as another development clone for purposes of merging incremental imports.

## Advanced Shared Repository Management

Git allows you to specify scripts called "hooks" to be run at certain points. You can use these, for example, to send all commits to the shared repository to a mailing list. See [githooks(5)](githooks.html).

You can enforce finer grained permissions using update hooks. See [Controlling access to branches using update hooks](howto/update-hook-example.html).

## Providing CVS Access to a Git Repository

It is also possible to provide true CVS access to a Git repository, so that developers can still use CVS; see [git-cvsserver(1)](git-cvsserver.html) for details.

## Alternative Development Models

CVS users are accustomed to giving a group of developers commit access to a common repository. As we’ve seen, this is also possible with Git. However, the distributed nature of Git allows other development models, and you may want to first consider whether one of them might be a better fit for your project.

For example, you can choose a single person to maintain the project’s primary public repository. Other developers then clone this repository and each work in their own clone. When they have a series of changes that they’re happy with, they ask the maintainer to pull from the branch containing the changes. The maintainer reviews their changes and pulls them into the primary repository, which other developers pull from as necessary to stay coordinated. The Linux kernel and other projects use variants of this model.

With a small group, developers may just pull changes from each other’s repositories without the need for a central maintainer.

## SEE ALSO

[gittutorial(7)](gittutorial.html), [gittutorial-2(7)](gittutorial-2.html), [gitcore-tutorial(7)](gitcore-tutorial.html), [gitglossary(7)](gitglossary.html), [giteveryday(7)](giteveryday.html), [The Git User’s Manual](user-manual.html)

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
