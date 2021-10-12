Full Git Guide:
===============

Install Git
===========

How to install Git on any OS

Git can be installed on the most common operating systems like Windows, Mac, and Linux. In fact, Git comes installed by default on most Mac and Linux machines!

Checking for Git
----------------

To see if you already have Git installed, open up your terminal application.

-   If you’re on a Mac, look for a command prompt application called “Terminal”.
-   If you’re on a Windows machine, open the windows command prompt or “Git Bash”.

Once you’ve opened your terminal application, type `git version`. The output will either tell you which version of Git is installed, or it will alert you that `git` is an unknown command. If it’s an unknown command, read further and find out how to install Git.

Install Git Using GitHub Desktop
--------------------------------

Installing GitHub Desktop will also install the latest version of Git if you don’t already have it. With GitHub Desktop, you get a command-line version of Git with a robust GUI. Regardless of if you have Git installed or not, GitHub Desktop offers a simple collaboration tool for Git. You can [learn more here](https://desktop.github.com/).

Install Git on Windows
----------------------

1.  Navigate to the latest [Git for Windows installer](https://gitforwindows.org/) and download the latest version.
2.  Once the installer has started, follow the instructions as provided in the **Git Setup** wizard screen until the installation is complete.
3.  Open the windows command prompt (or **Git Bash** if you selected not to use the standard Git Windows Command Prompt during the Git installation).
4.  Type `git version` to verify Git was installed.

Note: [`git-scm`](https://git-scm.com/download/win) is a popular and recommended resource for downloading Git for Windows. The advantage of downloading Git from `git-scm` is that your download automatically starts with the latest version of Git included with the recommended command prompt, `Git Bash` . The download source is the same [Git for Windows installer](https://gitforwindows.org/) as referenced in the steps above.

Install Git on Windows through Visual Studio Code
-------------------------------------------------

GitHub integration is provided through the [GitHub Pull Requests and Issues extension](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github). To get started with the GitHub in VS Code, you’ll need to create an account and install the GitHub Pull Requests and Issues extension. Once you’ve installed the [GitHub Pull Requests and Issues extension](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github), you’ll need to sign in. Follow the prompts to authenticate with GitHub and return to VS Code.

------------------------------------------------------------------------

Note: You can perform actions like, you can search for and clone a repository from GitHub using the Git: Clone command in the Command Palette (Ctrl+Shift+P) or by using the Clone Repository button in the Source Control view (available when you have no folder open). [Learn more here](https://code.visualstudio.com/docs/editor/github)

------------------------------------------------------------------------

Install Git on Mac
------------------

Most versions of MacOS will already have `Git` installed, and you can activate it through the terminal with `git version`. However, if you don’t have Git installed for whatever reason, you can install the latest version of Git using one of several popular methods as listed below:

#### Install Git From an Installer

1.  Navigate to the latest [macOS Git Installer](https://sourceforge.net/projects/git-osx-installer/files/git-2.23.0-intel-universal-mavericks.dmg/download?use_mirror=autoselect) and download the latest version.
2.  Once the installer has started, follow the instructions as provided until the installation is complete.
3.  Open the command prompt “terminal” and type `git version` to verify Git was installed.

Note: [`git-scm`](https://git-scm.com/download/mac) is a popular and recommended resource for downloading Git on a Mac. The advantage of downloading Git from `git-scm` is that your download automatically starts with the latest version of Git. The download source is the same [macOS Git Installer](https://sourceforge.net/projects/git-osx-installer/files/git-2.23.0-intel-universal-mavericks.dmg/download?use_mirror=autoselect) as referenced in the steps above.

#### Install Git from Homebrew

[Homebrew](https://brew.sh/) is a popular package manager for macOS. If you already have Homebrew installed, you can follow the below steps to install Git:

1.  Open up a terminal window and install Git using the following command: `brew install git`.
2.  Once the command output has been completed, you can verify the installation by typing: `git version`.

Install Git on Linux
--------------------

Fun fact: Git was originally developed to version the Linux operating system! So, it only makes sense that it is easy to configure to run on Linux.

You can install `Git` on Linux through the package management tool that comes with your distribution.

#### Debian/Ubuntu

1.  Git packages are available using `apt`.
2.  It’s a good idea to make sure you’re running the latest version. To do so, Navigate to your command prompt shell and run the following command to make sure everything is up-to-date: `sudo apt-get update`.
3.  To install Git, run the following command: `sudo apt-get install git-all`.
4.  Once the command output has been completed, you can verify the installation by typing: `git version`.

#### Fedora

1.  Git packages are available using `dnf`.
2.  To install Git, navigate to your command prompt shell and run the following command: `sudo dnf install git-all`.
3.  Once the command output has been completed, you can verify the installation by typing: `git version`.

Note: You can download the proper Git versions and read more about how to install on specific Linux systems, like installing Git on Ubuntu or Fedora, [in git-scm’s documentation](https://git-scm.com/download/linux).

Other Methods of Installing Git
-------------------------------

Looking to install Git via the source code? [Learn more here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

------------------------------------------------------------------------

------------------------------------------------------------------------

&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt; &lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------

------------------------------------------------------------------------

Git Guide
=========

Everything you need to know about Git, from getting started to advanced commands and workflows.

**Quick links:**

-   [What is Git?](#what-is-git)
-   [What is Git Written in?](#what-is-git-written-in)
-   [Why Use Git?](#why-use-git)
    -   [Speed](#speed)
    -   [Merge conflicts](#merge-conflicts)
    -   [Cheap branches](#cheap-branches)
    -   [Ease of roll back](#ease-of-roll-back)
-   [How Do I Use Git?](#how-do-i-use-git)
    -   [Learning Git Basics](#learning-git-basics)
    -   [Getting Started With the Git Workflow](#getting-started-with-the-git-workflow)
        -   [Create a branch](#create-a-branch)
        -   [Make changes (and make a commit)](#make-changes-and-make-a-commit)
        -   [Push your changes to the remote](#push-your-changes-to-the-remote)
        -   [Open a pull request](#open-a-pull-request)
        -   [Collaborate](#collaborate)
        -   [Merge into main](#merge-into-main)
    -   [Getting Started With GitHub](#getting-started-with-github)

What is Git?
------------

Git is a distributed version control software. Version control is a way to save changes over time without overwriting previous versions. Being distributed means that every developer working with a Git repository has a copy of that entire repository - every commit, every branch, every file. If you’re used to working with centralized version control systems, this is a big difference!

Whether or not you’ve worked with version control before, there are a few things you should know before getting started with Git:

-   Branches are lightweight and cheap, so it’s OK to have many of them
-   Git stores changes in SHA hashes, which work by compressing text files. That makes Git a very good version control system (VCS) for software programming, but not so good for binary files like images or videos.
-   Git repositories can be connected, so you can work on one locally on your own machine, and connect it to a shared repository. This way, you can [push](/git-guides/git-push) and [pull](/git-guides/git-pull) changes to a repository and easily collaborate with others.

What is Git Written in?
-----------------------

The tools that make up the core Git distribution are written in C, Shell, Perl, and Tcl. You can find Git’s source code on GitHub under [git/git](https://github.com/git/git).

Why Use Git?
------------

Version control is very important - without it, you risk losing your work. With Git, you can make a “commit”, or a save point, as often as you’d like. You can also go back to previous commits. This takes the pressure off of you while you’re working. Commit often and commit early, and you’ll never have that gut-sinking feeling of overwriting or losing changes.

There are many version control systems out there - but Git has some major advantages.

### Speed

Like we mentioned above, Git uses SHA compression, which makes it very fast.

### Merge conflicts

Git can handle merge conflicts, which means that **it’s OK for multiple people to work on the same file at the same time**. This opens up the world of development in a way that isn’t possible with centralized version control. You have access to the entire project, and if you’re working on a branch, you can do whatever you need to and know that your changes are safe.

### Cheap branches

Speaking of branches, Git offers a lot of flexibility and opportunity for collaboration with branches. **By using branches, developers can make changes in a safe sandbox.**

Instead of only committing code that is 100% sure to succeed, developers can commit code that might still need help. Then, they can push that code to the remote and get fast feedback from integrated tests or peer review.

Without sharing the code through branches, this would never be possible.

### Ease of roll back

If you make a mistake, it’s OK! Commits are immutable, meaning they can’t be changed. (*Note: You *can* change history, but it will create new replacement commits instead of editing the existing commits. More on that later!*) This means that if you do make a mistake, even on an important branch, like `main`, it’s *OK*. **You can easily revert that change, or roll back the branch pointer to the commit where everything was fine.**

The benefits of this can’t be overstated. Not only does it create a safer environment for the project and code, but it fosters a development environment where developers can be braver, trusting that Git has their back.

How Do I Use Git?
-----------------

### Learning Git Basics

If you’re getting started with Git, a great place to learn the basic commands is the [Git Cheat sheet](https://github.github.io/training-kit/). It’s translated into many languages, [open source as a part of the `github/training-kit` repository](https://github.com/github/training-kit), and a great starting place for the fundamentals on the command line.

Some of the most important and most used commands that you’ll find there are:

-   `git clone [url]`: [Clone](/git-guides/git-clone) (download) a repository that already exists on GitHub, including all of the files, branches, and commits.
-   `git status`: Always a good idea, this command shows you what branch you’re on, what files are in the working or staging directory, and any other important information.
-   `git branch`: This shows the existing branches in your local repository. You can also use `git branch [branch-name]` to create a branch from your current location, or `git branch --all` to see all branches, both the local ones on your machine, and the remote tracking branches stored from the last `git pull` or `git fetch` from the remote.
-   `git checkout [branch-name]`: Switches to the specified branch and updates the working directory.
-   `git add [file]`: Snapshots the file in preparation for versioning, adding it to the staging area.
-   `git commit -m "descriptive message"`: Records file snapshots permanently in the version history.
-   `git pull`: Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. `git pull` is a combination of `git fetch` and `git merge`.
-   `git push`: Uploads all local branch commits to the remote.
-   `git log`: Browse and inspect the evolution of project files.
-   `git remote -v`: Show the associated remote repositories and their stored name, like `origin`.

If you’re looking for more GitHub-specific technical guidance, check out [GitHub’s help documentation](https://help.github.com/) or our [GitHub for Developers series](https://www.youtube.com/watch?v=H6wTAIlOUBQ&list=PLg7s6cbtAD16Pgp6WIVfX4VsGI-xyWkMz) on YouTube.

### Getting Started With the Git Workflow

Depending on your operating system, you may already have [Git installed](/git-guides/install-git). But, getting started means more than having the software! To get started, it’s important to know the basics of how Git works. You may choose to do the actual work within a terminal, an app like GitHub Desktop, or through GitHub.com. (*Note: while you can interact with Git through GitHub.com, your experience may be limited. Many local tools can give you access to the most widely used Git functionalities, though only the terminal will give you access to them all.*)

There are *many* ways to use Git, which doesn’t necessarily make it easier! But, the fundamental Git workflow has a few main steps. You can practice all of these in the [Introduction to GitHub Learning Lab course](https://lab.github.com/githubtraining/introduction-to-github).

#### Create a branch

The main branch is usually called `main`. We want to work on *another* branch, so we can make a pull request and make changes safely. To get started, create a branch off of `main`. Name it however you’d like - but we recommend naming branches based on the function or feature that will be the focus of this branch. One person may have several branches, and one branch may have several people collaborate on it - branches are for a purpose, not a person. Wherever you currently “are” (wherever HEAD is pointing, or whatever branch you’re currently “checked out” to) will be the parent of the branch you create. That means you can create branches from other branches, tags, or any commit! But, the most typical workflow is to create a branch from `main` - which represents the most current production code.

#### Make changes (and make a commit)

Once you’ve created a branch, and moved the HEAD pointer to it by “checking out” to that branch, you’re ready to get to work. Make the changes in your repository using your favorite text editor or IDE.

Next, save your changes. You’re ready to start the commit!

To start your [commit](/git-guides/git-commit), you need to let Git know what changes you’d like to include with `git add [file]`.

Once you’ve saved and staged the changes, you’re ready to [make the commit](/git-guides/git-commit) with `git commit -m "descriptive commit message"`.

#### Push your changes to the remote

So far, if you’ve made a commit locally, you’re the only one that can see it. To let others see your work and begin collaboration, you should “push” your changes using `git push`. If you’re pushing from a branch for the first time that you’ve created locally, you may need to give Git some more information. `git push -u origin [branch-name]` tells Git to push the current branch, and create a branch on the remote that matches it with the same name - and also, create a relationship with that branch so that `git push` will be enough information in the future.

By default, `git push` only pushes the branch that you’ve currently checked out to.

Sometimes, if there has been a new commit on the branch on the *remote*, you may be blocked from pushing. Don’t worry! Start with a simple [`git pull`](/git-guides/git-pull) to incorporate the changes on the remote into your own local branch, resolve any conflicts or finish the merge from the remote into the local branch, and then try the push again.

#### Open a pull request

Pushing a branch, or new commits, to a remote repository is enough if a pull request already exists, but if it’s the first time you’re pushing that branch, you should open a new pull request. A pull request is a comparison of two branches - typically `main`, or the branch that the feature branch was created from, and the feature branch. This way, like branches, pull requests are scoped around a specific function or addition of work, rather than the person making the changes or the amount of time the changes will take.

Pull requests are the powerhouse of GitHub. Integrated tests can automatically run on pull requests, giving you immediate feedback on your code. Peers can give detailed code reviews, letting you know if there are changes to make, or if it’s ready to go.

Make sure you start your pull requests off with the right information. Put yourself in the shoes of your teammates, or even of your future self. Include information about what this change relates to, what prompted it, what is already done, what is left to do, and any specific asks for help or reviews. Include links to relevant work or conversations. Pull request templates can help make this process easy by automating the starting content of the body of pull requests.

#### Collaborate

Once the pull request is open, then the real fun starts. It’s important to recognize that pull requests aren’t meant to be open when work is *finished*. Pull requests should be open when work is *beginning*! The earlier you open a pull request, the more visibility the entire team has to the work that you’re doing. When you’re ready for feedback, you can get it by integrating tests or requesting reviews from teammates.

It’s very likely that you will want to make more changes to your work. That’s great! To do that, make more commits on the same branch. Once the new commits are present on the remote, the pull request will update and show the most recent version of your work.

#### Merge into `main`

Once you and your team decide that the pull request looks good, you can merge it. By merging, you integrate the feature branch into the other branch (most typically the `main` branch). Then, `main` will be updated with your changes, and your pull request will be closed. Don’t forget to delete your branch! You won’t need it anymore. Remember, branches are lightweight and cheap, and you should create a new one when you need it based on the most recent commit on the `main` branch.

If you choose not to merge the pull request, you can also close pull requests with unmerged changes.

### Getting Started With GitHub

If you’re wondering where Git ends and GitHub begins, you’re not alone. They are tied closely together to make working with them both a seamless experience. While Git takes care of the underlying version control, GitHub is the collaboration platform built on top of it. GitHub is the place for pull requests, comments, reviews, integrated tests, and so much more. Most developers work locally to develop and use GitHub for collaboration. That ranges from using GitHub to host the shared remote repository to working with colleagues and capitalizing on features like protected branches, code review, GitHub Actions, and more.

The best place to practice using Git and GitHub is the [Introduction to GitHub Learning Lab course](https://lab.github.com/githubtraining/introduction-to-github).

If you already know Git and need to sign up for a GitHub account, head over to [github.com](https://github.com/).

------------------------------------------------------------------------

------------------------------------------------------------------------

&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt; &lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------

------------------------------------------------------------------------

Git Status
==========

    git status

`git status` shows the current state of your Git working directory and staging area.

What Does `git status` Do?
--------------------------

When in doubt, run `git status`. This is *always* a good idea. The `git status` command only outputs information, it won’t modify commits or changes in your local repository.

A useful feature of `git status` is that it will provide helpful information depending on your current situation. In general, you can count on it to tell you:

-   Where `HEAD` is pointing, whether that is a branch or a commit (this is where you are “checked out” to)
-   If you have any changed files in your current directory that have not yet been committed
-   If changed files are staged or not
-   If your current local branch is linked to a remote branch, then `git status` will tell you if your local branch is behind or ahead by any commits

During merge conflicts, `git status` will also tell you exactly which files are the source of the conflict.

How to Use `git status`
-----------------------

### Common usages and options for `git status`

-   `git status`: Most often used in its default form, this shows a good base of information
-   `git status -s`: Give output in short format
-   `git status -v`: Shows more “verbose” detail including the textual changes of any uncommitted files

You can see all of the options with `git status` in [git-scm’s documentation](https://git-scm.com/docs/git-status).

Related Terms
-------------

-   `git clone [url]`: Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits.
-   `git remote -v`: Show the associated remote repositories and their stored name, like `origin`.
-   `git remote add origin <url>`: Add a remote so you can collaborate with others on a newly initialized repository.
-   `git push`: Uploads all local branch commits to the remote.
-   `git push -u origin main`: When pushing a branch for the first time, this type of push will configure the relationship between the remote and your local repository so that you can use `git pull` and `git push` with no additional options in the future.

------------------------------------------------------------------------

------------------------------------------------------------------------

&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt; &lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------

------------------------------------------------------------------------

Git Clone
=========

The `git clone` command is used to create a copy of a specific repository or branch within a repository.

Git is a distributed version control system. Maximize the advantages of a full repository on your own machine by cloning.

### What Does `git clone` Do?

    git clone https://github.com/github/training-kit.git

When you clone a repository, you don’t get one file, as you may in other centralized version control systems. By cloning with Git, you get the entire repository - all files, all branches, and all commits.

Cloning a repository is typically only done once, at the beginning of your interaction with a project. Once a repository already exists on a remote, like on GitHub, then you would clone that repository so you could interact with it locally. Once you have cloned a repository, you won’t need to clone it again to do regular development.

The ability to work with the entire repository means that all developers can work more freely. Without being limited by which files you can work on, you can work on a feature branch to make changes safely. Then, you can:

-   later use `git push` to share your branch with the remote repository
-   open a pull request to compare the changes with your collaborators
-   test and deploy as needed from the branch
-   merge into the `main` branch.

How to Use `git clone`
----------------------

### Common usages and options for `git clone`

-   `git clone [url]`: Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits.
-   `git clone --mirror`: Clone a repository but without the ability to edit any of the files. This includes the refs or branches. You may want to use this if you are trying to create a secondary copy of a repository on a separate remote and you want to match all of the branches. This may occur during configuration using a new remote for your Git hosting, or when using Git during automated testing.
-   `git clone --single-branch`: Clone only a single branch
-   `git clone --sparse`: Instead of populating the working directory with all of the files in the current commit recursively, only populate the files present in the root directory. This could help with performance when cloning large repositories with many directories and sub-directories.
-   \`git clone –recurse-submodules\[=&lt;pathspec\]: After the clone is created, initialize and clone submodules within based on the provided pathspec. This may be a good option if you are cloning a repository that you know to have submodules, and you will be working with those submodules as dependencies in your local development.

You can see all of the many options with `git clone` in [git-scm’s documentation](https://git-scm.com/docs/git-clone).

Examples of `git clone`
-----------------------

### `git clone [url]`

The most common usage of cloning is to simply clone a repository. This is only done once, when you begin working on a project, and would follow the syntax of `git clone [url]`.

### `git clone` A Branch

`git clone --single-branch`: By default, `git clone` will create remote tracking branches for all of the branches currently present in the remote which is being cloned. The only local branch that is created is the default branch.

But, maybe for some reason, you would like to *only* get a remote tracking branch for one specific branch, or clone one branch which *isn’t* the default branch. Both of these things happen when you use `--single-branch` with `git clone`.

This will create a clone that only has commits included in the current line of history. This means no other branches will be cloned. You can specify a certain branch to clone, but the default branch, usually `main`, will be selected by default.

To clone one specific branch, use:

`git clone [url] --branch [branch] --single-branch`

*Cloning only one branch does not add any benefits unless the repository is very large and contains binary files that slow down the performance of the repository. The recommended solution is to optimize the performance of the repository before relying on single branch cloning strategies.*

### `git clone` With SSH

Depending on how you authenticate with the remote server, you may choose to clone using SSH.

If you choose to clone with SSH, you would use a specific SSH path for the repository instead of a URL. Typically, developers are authenticated with SSH from the machine level. This means that you would probably clone with HTTPS or with SSH - not a mix of both for your repositories.

Related Terms
-------------

-   `git branch`: This shows the existing branches in your local repository. You can also use `git branch [branch-name]` to create a branch from your current location, or `git branch --all` to see all branches, both the local ones on your machine and the remote tracking branches stored from the last `git pull` or `git fetch` from the remote.
-   `git pull`: Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. `git pull` is a combination of `git fetch` and `git merge`.
-   `git push`: Uploads all local branch commits to the remote.
-   `git remote -v`: Show the associated remote repositories and their stored name, like `origin`.

------------------------------------------------------------------------

------------------------------------------------------------------------

&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt; &lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------

------------------------------------------------------------------------

Git Add
=======

The `git add` command adds new or changed files in your working directory to the Git staging area.

`git add` is an important command - without it, no `git commit` would ever do anything. Sometimes, `git add` can have a reputation for being an unnecessary step in development. But in reality, `git add` is an important and powerful tool. `git add` allows you to shape history without changing how you work.

![image of working directory, staging area, and committed history with commands shown and visualized]()

When do you use `git add`?
--------------------------

    git add README.md

As you’re working, you change and save a file, or multiple files. Then, before you commit, you must `git add`. This step allows you to choose what you are going to commit. Commits should be logical, atomic units of change - but not everyone works that way. Maybe you are making changes to files that *aren’t* logical or atomic units of change. `git add` allows you to systematically shape your commits and your history anyway.

### What Does Git Add Do?

`git add [filename]` selects that file, and moves it to the staging area, marking it for inclusion in the next commit. You can select all files, a directory, specific files, or even specific parts of a file for staging and commit.

This means if you `git add` a deleted file the *deletion* is staged for commit. The language of “add” when you’re actually “deleting” can be confusing. If you think or use `git stage` in place of `git add`, the reality of what is happening may be more clear.

`git add` and `git commit` go together hand in hand. They don’t work when they aren’t used together. And, they both work best when used thinking of their joint functionality.

How to Use `git add`
--------------------

### Common usages and options for `git add`

-   `git add <path>`: Stage a specific directory or file
-   `git add .`: Stage all files (that are not listed in the `.gitignore`) in the entire repository
-   `git add -p`: Interactively stage hunks of changes

You can see all of the many options with `git add` in [git-scm’s documentation](https://git-scm.com/docs/git-add).

Examples of `git add`
---------------------

`git add` usually fits into the workflow in the following steps:

1.  Create a branch: `git branch update-readme`
2.  Checkout to that branch: `git checkout update-readme`
3.  Change a file or files
4.  Save the file or files
5.  Add the files or segments of code that should be included in the next commit: `git add README.md`
6.  Commit the changes: `git commit -m "update the README to include links to contributing           guide"`
7.  Push the changes to the remote branch: `git push -u origin update-readme`

But, `git add` could also be used like:

1.  Create a branch: `git branch update-readme`
2.  Checkout to that branch: `git checkout update-readme`
3.  Change a file or files
4.  Save the file or files
5.  Add only one file, or one part of the changed file: `git add README.md`
6.  Commit the first set of changes: `git commit -m "update the README to include links to contributing           guide"`
7.  Add another file, or another part of the changed file: `git add CONTRIBUTING.md`
8.  Commit the second set of changes: `git commit -m "create the contributing guide"`
9.  (Repeat as necessary)
10. Push the changes to the remote branch: `git push -u origin update-readme`

### `git add` All Files

Staging all available files is a popular, though risky, operation. This can save time, but the risks are two-fold:

#### Poorly thought out history

By staging all available changes, the clarity of your history will likely suffer. Being able to shape your history is one of the greatest advantages of using Git. If your commits are too large, contain unrelated changes, or are unclearly described in the commit message, you will lose the benefits of viewing and changing history.

#### Accidentally staging and committing files

By using an option to add all files at once, you may accidentally stage and commit a file. Most common flags don’t add files tracked in the `.gitignore` file. But, any file not listed in the `.gitignore` file will be staged and committed. This applies to large binary files, and files containing sensitive information like passwords or authentication tokens.

#### Deciding to stage all files

If the time is right to stage all files, there are several commands that you can choose from. As always, it’s very important to know what you are staging and committing.

-   `git add -A`: stages all files, including new, modified, and deleted files, including files in the current directory *and* in higher directories that still belong to the same git repository
-   `git add .`: adds the entire directory recursively, including files whose names begin with a dot
-   `git add -u`: stages modified and deleted files only, NOT new files

<table style="width:96%;"><colgroup><col style="width: 10%" /><col style="width: 7%" /><col style="width: 11%" /><col style="width: 10%" /><col style="width: 30%" /><col style="width: 14%" /><col style="width: 14%" /></colgroup><thead><tr class="header"><th></th><th>New files</th><th>Modified files</th><th>Deleted files</th><th>Files with names beginning with a dot</th><th>Current directory</th><th>Higher directories</th></tr></thead><tbody><tr class="odd"><td><code>git add -A</code></td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr class="even"><td><code>git add .</code></td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td></tr><tr class="odd"><td><code>git add -u</code></td><td>No</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr></tbody></table>

### `git add` A Folder or Specific File

The safest and clearest way to use `git add` is by designating the specific file or directory to be staged. The syntax for this could look like:

`git add directory/`: Stage all changes to all files within a directory titled `directory` `git add README.md`: Stage all changes within the `README.md` file

### Undo Added Files

Before undoing a `git add`, you should first be sure that you won’t lose any work. There’s no way to “revert” an add in the same way you can revert a commit, but you can move the files out of the staging area.

For example, if you have a staged file, and then you make more changes to that file in your working directory. Now, the versions in your working directory and your staging area are different. If you take action to remove the changed version of the file from the staging area, the changes that were in your working directory *but not* staged will be overwritten.

To avoid this, first stage all changes, then unstage them together, or commit the changes and reset back before the commit happened.

#### Using `git reset` to undo `git add`

`git reset` is a flexible and powerful command. One of its many use cases is to move changes *out* of the staging area. To do this, use the “mixed” level of reset, which is the default.

To move staged changes from the staging area to the working directory without affecting committed history, first make sure that you don’t have any additional changes to the files in question as mentioned above. Then, type `git reset HEAD` (aka `git reset --mixed HEAD`).

Related Terms
-------------

-   `git status`: Always a good idea, this command shows you what branch you’re on, what files are in the working or staging directory, and any other important information.
-   `git checkout [branch-name]`: Switches to the specified branch and updates the working directory.
-   `git commit -m "descriptive message"`: Records file snapshots permanently in version history.
-   `git push`: Uploads all local branch commits to the remote.

------------------------------------------------------------------------

------------------------------------------------------------------------

&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt; &lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------

------------------------------------------------------------------------

Git Commit
==========

`git commit` creates a commit, which is like a snapshot of your repository. These commits are snapshots of your entire repository at specific times. You should make new commits often, based around logical units of change. Over time, commits should tell a story of the history of your repository and how it came to be the way that it currently is. Commits include lots of metadata in addition to the contents and message, like the author, timestamp, and more.

How Git Commit Works
--------------------

Commits are the building blocks of “save points” within Git’s version control.

    git commit -m "update the README.md with link to contributing guide"

### Commits shape history

By using commits, you’re able to craft history intentionally and safely. You can make commits to different branches, and specify exactly what changes you want to include. Commits are created on the branch that you’ve currently checked out to (wherever HEAD is pointing) so it’s always a good idea to run `git status` before making a commit, to check that you’re checked out to the branch that you intend to be. Before you commit, you will need to stage any new changes that you’d like to include in the commit using `git add [file]`.

Commits are lightweight SHA hashes, objects within Git. As long as you’re working with text files, you won’t need to worry about how many files you have, how big they are, or how many commits you make. Git can handle it!

### Committing in two phases

Commits have two phases to help you craft commits properly. Commits should be logical, atomic units of change that represent a specific idea. But, not all humans work that way. You may get carried away and end up solving two or three problems before you remember to commit! That’s OK - Git can handle that. Once you’re ready to craft your commits, you’ll use `git add <FILENAME>` to specify the files that you’d like to “stage” for commit. Without adding any files, the command `git commit` won’t work. Git only looks to the staging area to find out what to commit. Staging, or adding, files, is possible through the command line, and also possible with most Git interfaces like GitHub Desktop by selecting the lines or files that you’d like to stage.

You can also use a handy command, `git add -p`, to walk through the changes and separate them, even if they’re in the same file.

How to Use Git Commit
---------------------

### Common usages and options for Git Commit

-   `git commit`: This starts the commit process, but since it doesn’t include a `-m` flag for the message, your default text editor will be opened for you to create the commit message. If you haven’t configured anything, there’s a good chance this will be VI or Vim. (To get out, press Esc, then `:wq`, and then Enter. :wink:)
-   `git commit -m "descriptive commit message"`: This starts the commit process, and allows you to include the commit message at the same time.
-   `git commit -am "descriptive commit message"`: In addition to including the commit message, this option allows you to skip the staging phase. The addition of `-a` will automatically stage any files that are already being tracked by Git (changes to files that you’ve committed before).
-   `git commit --amend`: Replaces the most recent commit with a new commit. (More on this later!)

To see all of the possible options you have with `git commit`, check out [Git’s documentation](https://git-scm.com/docs/git-commit).

### How to Undo Commits in Git

Sometimes, you may need to change history. You may need to undo a commit. If you find yourself in this situation, there are a few very important things to remember:

-   If you are “undoing” a commit that exists on the remote, you could create big problems for your collaborators
-   Undoing a commit on work that you only have locally is much safer

### What can go wrong while changing history?

Changing history for collaborators can be problematic in a few ways. Imagine - You and another collaborator have the same repository, with the same history. But, they make a change that *deletes* the most recent commit. They continue new commits from the commit directly before that. Meanwhile, you keep working *with* the commit that the collaborator tried to delete. When they push, they’ll have to ‘force push’, which should show to them that they’re changing history. **What do you think will happen when you try to push?**

In dramatic cases, Git may decide that the histories are too different and the projects are no longer related. This is uncommon, but a big problem.

The most common result is that your `git push` would return the “deleted” commit to a shared history. (First, you would `git pull` if you were working on the same branch, and then merge, but the results would be the same.) This means that whatever was so important to delete is now back in the repository. A password, token, or large binary file may return without ever alerting you.

#### `git revert`

`git revert` is the safest way to change history with Git. Instead of deleting existing commits, `git revert` looks at the changes introduced in a specific commit, then applies the inverse of those changes in a new commit. It functions as an “undo commit” command, without sacrificing the integrity of your repository’s history. **`git revert` is always the recommended way to change history when it’s possible**.

#### `git reset`

Sometimes, a commit includes sensitive information that actually needs to be deleted. `git reset` is a very powerful command that may cause you to lose work. By resetting, you move the `HEAD` pointer and the branch pointer to another point in time - maybe making it seem like the commits in between never happened! Before using `git reset`:

-   Make sure to talk with your team about any shared commits
-   Research the three types of reset to see which is right for you (–soft, –mixed, –hard)
-   Commit any work that you don’t want to be lost intentionally - work that is committed can be gotten back, but uncommitted work cannot

#### `git reflog`

If you’re changing history and undoing commits, you should know about `git reflog`. If you get into trouble, the reflog could get you out of trouble. The reflog is a log of every commit that `HEAD` has pointed to. So, for example, if you use `git reset` and unintentionally lose commits, you can find and access them with `git reflog`.

### Updating Commits With Git Commit Amend

While `git commit --amend` does change history, it only changes the most recent commit on your current branch. This can be an extremely useful command for commits that:

-   Haven’t been pushed to the remote yet
-   Have a spelling error in the commit message
-   Don’t contain the changes that you’d like to contain

Examples of Git Commit
----------------------

Once you’ve staged the files that you want to include in your commit, you’re ready. Whether you commit in a tool like GitHub Desktop, or through your command line, the commit message is important. Commit messages should be short and descriptive of your change. If you are looking through your repository’s history, you’ll be guided by the commit messages, so they should tell a story. Commits in the command line can include the message with the following format:

-   `git commit -m "git commit message example"`

Commit messages should be present tense and directive, like the following examples:

-   `git commit -m "create file structure for Git guides"`
-   `git commit -m "translate Git cheat sheet into German"`
-   `git commit -m "update broken URL to Git resources"`

If you’d like to include more context in your commit messages, you can also include an extended commit message.

Related commands
----------------

-   `git add [file]`: Snapshots the file in preparation for versioning, adding it to the staging area.
-   `git status`: Always a good idea, this command shows you what branch you’re on, what files are in the working or staging directory, and any other important information.
-   `git push`: Uploads all local branch commits to the remote.
-   `git log`: Browse and inspect the evolution of project files.

------------------------------------------------------------------------

------------------------------------------------------------------------

&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt; &lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------

------------------------------------------------------------------------

Git Push
========

    git push

`git push` uploads all local branch commits to the corresponding remote branch.

What Does `git push` Do?
------------------------

`git push` updates the remote branch with local commits. It is one of the four commands in Git that prompts interaction with the remote repository. You can also think of `git push` as *update* or *publish*.

By default, `git push` only updates the corresponding branch on the remote. So, if you are checked out to the `main` branch when you execute `git push`, then only the `main` branch will be updated. It’s always a good idea to use `git status` to see what branch you are on before pushing to the remote.

How to Use `git push`
---------------------

After you make and commit changes locally, you can share them with the remote repository using `git push`. Pushing changes to the remote makes your commits accessible to others who you may be collaborating with. This will also update any open pull requests with the branch that you’re working on.

As best practice, it’s important to run the `git pull` command before you push any new changes to the remote branch. This will update your local branch with any new changes that may have been pushed to the remote from other contributors. Pulling before you push can reduce the amount of merge conflicts you create on GitHub - allowing you to resolve them locally before pushing your changes to the remote branch.

### Common usages and options for `git push`

-   `git push -f`: Force a push that would otherwise be blocked, usually because it will delete or overwrite existing commits *(Use with caution!)*
-   `git push -u origin [branch]`: Useful when pushing a new branch, this creates an upstream tracking branch with a lasting relationship to your local branch
-   `git push --all`: Push all branches
-   `git push --tags`: Publish tags that aren’t yet in the remote repository

You can see all of the options with `git push` in [git-scm’s documentation](https://git-scm.com/docs/git-push).

Why can’t I push?
-----------------

If you are trying to `git push` but are running into problems, there are a few common solutions.

### Check your branch

Check what branch you are currently on with `git status`. If you are working on a protected branch, like `main`, you may be unable to push commits directly to the remote. If this happens to you, it’s OK! You can fix this a few ways.

#### Work was not yet on any branch

1.  Create and checkout to a new branch from your current commit: `git checkout -b [branchname]`
2.  Then, push the new branch up to the remote: `git push -u origin [branchname]`

#### Accidentally committed to the wrong branch

1.  Checkout to the branch that you intended to commit to: `git checkout [branchname]`
2.  Merge the commits from the branch that you *did* accidentally commit to: `git merge [main]`
3.  Push your changes to the remote: `git push`
4.  Fix the other branch by checking out to that branch, finding what commit it *should* be pointed to, and using `git reset --hard` to correct the branch pointer

Related Terms
-------------

-   `git commit -m "descriptive message"`: Records file snapshots permanently in version history.
-   `git clone [url]`: Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits.
-   `git status`: Always a good idea, this command shows you what branch you’re on, what files are in the working or staging directory, and any other important information.
-   `git pull`: Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. `git pull` is a combination of `git fetch` and `git merge`.

------------------------------------------------------------------------

------------------------------------------------------------------------

&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt; &lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------

------------------------------------------------------------------------

Git Pull
========

`git pull` updates your current local working branch and all of the remote tracking branches. It’s a good idea to run `git pull` regularly on the branches you are working on locally.

Without `git pull`, (or the effect of it,) your local branch wouldn’t have any of the updates that are present on the remote.

### What Does `git pull` Do?

    git pull

`git pull` is one of the 4 remote operations within Git. Without running `git pull`, your local repository will never be updated with changes from the remote. `git pull` should be used every day you interact with a repository with a remote, at the minimum. That’s why `git pull` is one of the most used Git commands.

### `git pull` and `git fetch`

`git pull`, a combination of `git fetch` + `git merge`, updates some parts of your local repository with changes from the remote repository. To understand what is and isn’t affected by `git pull`, you need to first understand the concept of remote tracking branches. When you clone a repository, you clone one working branch, `main`, and all of the remote tracking branches. `git fetch` updates the remote tracking branches. `git merge` will update your current branch with any new commits on the remote tracking branch.

`git pull` is the most common way to update your repository.

However, you may want to use `git fetch` instead. One reason to do this may be that you expect conflicts. Conflicts can occur in this way if you have new local commits and new commits on the remote. Just like a merge conflict that would happen between two different branches, these two different lines of history could contain changes to the same parts of the same file. If you first operate `git fetch`, the merge won’t be initiated, and you won’t be prompted to solve the conflict. This gives you the flexibility to resolve the conflict later without the need for network connectivity.

Another reason you may want to run `git fetch` is to update to all remote tracking branches before losing network connectivity. If you run `git fetch`, and then later try to run `git pull` without any network connectivity, the `git fetch` portion of the `git pull` operation will fail.

If you do use `git fetch` instead of `git pull`, make sure you remember to `git merge`. Merging the remote tracking branch into your own branch ensures you will be working with any updates or changes.

How to Use `git pull`
---------------------

### Common usages and options for `git pull`

-   `git pull`: Update your local working branch with commits from the remote, *and* update all remote tracking branches.
-   `git pull --rebase`: Update your local working branch with commits from the remote, but rewrite history so any local commits occur after all new commits coming from the remote, avoiding a merge commit.
-   `git pull --force`: This option allows you to force a fetch of a specific remote tracking branch when using the `<refspec>` option that would otherwise not be fetched due to conflicts. To force Git to overwrite your current branch to match the remote tracking branch, read below about using `git reset`.
-   `git pull --all`: Fetch *all* remotes - this is handy if you are working on a fork or in another use case with multiple remotes.

You can see all of the many options with `git pull` in [git-scm’s documentation](https://git-scm.com/docs/git-pull).

Examples of `git pull`
----------------------

### Working on a Branch

If you’re already working on a branch, it is a good idea to run `git pull` before starting work and introducing new commits. Even if you take a small break from development, there’s a chance that one of your collaborators has made changes to your branch. This change could even come from updating your branch with new changes from `main`.

It is always a good idea to run `git status` - especially before `git pull`. Changes that are not committed can be overwritten during a `git pull`. Or, they can block the `git merge` portion of the `git pull` from executing. If you have files that are changed, but not committed, and the changes on the remote also change those same parts of the same file, Git must make a choice. Since they are not committed changes, there is no possibility for a merge conflict. Git will either overwrite the changes in your working or staging directories, or the `merge` will not complete, and you will not be able to include any of the updates from the remote.

If this happens, use `git status` to identify what changes are causing the problem. Either delete or commit those changes, then `git pull` or `git merge` again.

### Keep `main` up to date

Keeping the `main` branch up to date is generally a good idea.

For example, let’s say you have cloned a repository. After you clone, someone merges a branch into main. Then, you’d like to create a new branch to do some work. If you create your branch off of `main` *before* operating `git pull`, your branch will not have the most recent changes. You could accidentally introduce a conflict or duplicate changes. By running `git pull` before you create a branch, you can be sure that you will be working with the most recent information.

### Undo A `git pull`

To effectively “undo” a `git pull`, you cannot undo the `git fetch` - but you can undo the `git merge` that changed your local working branch.

To do this, you will need to `git reset` to the commit you made *before* you merged. You can find this commit by searching the `git reflog`. The reflog is a log of every place that HEAD has pointed - every place that you have ever been checked out to. This reflog is only kept for 30 to 90 days, depending on the commit, and is only stored locally. *(The reflog is a great reason not to delete a repository if you think you’ve made a mistake!)*

Run `git reflog` and search for the commit that you would like to return to. Then, run `git reset --hard <SHA>` to reset HEAD and your current branch to the SHA of the commit from before the merge.

### Force `git pull` to Overwrite Local Files

If you have made commits locally that you regret, you may want your local branch to match the remote branch without saving any of your work. This can be done using `git reset`. First, make sure you have the most recent copy of that remote tracking branch by fetching.

`git fetch <remote> <branch>` ex: `git fetch origin main`

Then, use `git reset --hard` to move the HEAD pointer and the current branch pointer to the most recent commit as it exists on that remote tracking branch.

`git reset --hard <remote>/<branch>` ex: `git reset --hard origin/main`

> \_Note: You can find the remotes with `git remote -v`, and see all available remote tracking branches with `git branch --all`.

### `git pull` with Rebase

If there have been new commits on both your local branch and the remote branch, a merge commit will be created when you `git pull`. This recursive merge is the default merge style when there are two splits in history being brought together. But, you may want history on a branch to be only one line.

You can update your local working branch with commits from the remote, but rewrite history so any local commits occur after all new commits coming from the remote, avoiding a merge commit. This is done with `git pull --rebase`.

Using `git pull --rebase` does not affect the integrity of the changes or the commits, but it does affect how history looks in the commit parent/child relationship.

Related Terms
-------------

-   `git clone [url]`: Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits.
-   `git status`: Always a good idea, this command shows you what branch you’re on, what files are in the working or staging directory, and any other important information.
-   `git branch`: This shows the existing branches in your local repository. You can also use `git branch [banch-name]` to create a branch from your current location, or `git branch --all` to see all branches, both the local ones on your machine, and the remote tracking branches stored from the last `git pull` or `git fetch` from the remote.
-   `git push`: Uploads all local branch commits to the remote.
-   `git log`: Browse and inspect the evolution of project files.
-   `git remote -v`: Show the associated remote repositories and their stored name, like `origin`.

------------------------------------------------------------------------

------------------------------------------------------------------------

&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt; &lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;:&lt;:&gt;
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------

------------------------------------------------------------------------

Git Remote
==========

There are some operations with `git remote`, like `git remote -v`, that you may use occasionally.

But, the concept of a remote within Git is important and powers many of the other operations.

What does Git remote do?
------------------------

    git remote -v

`git remote` manages the set of remotes that you are tracking with your local repository.

### Common `git remote` commands

-   `git remote -v`: List the current remotes associated with the local repository
-   `git remote add [name] [URL]`: Add a remote
-   `git remote remove [name]`: Remove a remote

### What is `origin`?

If you try running `git remote -v` in your repositories, you’ll probably see something called `origin`. You may notice `origin` in many messages from Git. `origin` is the human-friendly name for the URL that the remote repository is stored at. It’s like a key-value pair, and `origin` is the default.

### What is `upstream`?

You may need or want to work with multiple remotes for one local repository. This can be common in open source when a contributor needs to create a fork of a repository to have permission to push changes to the remote.

In this case, it’s common to create and clone a fork. Then, the default remote would be `origin`, in reference to the fork. To make it easier to pull any changes to update the local copy of the fork from the original repository, many people add the original repository as a remote also. It’s typical to name this remote `upstream`.

![](https://user-images.githubusercontent.com/9906718/77051803-28625800-69cc-11ea-9533-b5387ed2d3b5.png)

Communicating with the remote
-----------------------------

There are four commands within Git that prompt communication with the remote. Unless you are using one of these four commands, all of your work is only happening locally.

-   `git push`
-   `git clone`
-   `git pull`
-   `git fetch`

Branches and the remote
-----------------------

The concept of branches can be confusing once it is combined with the concept of remotes. Git keeps track of the branches that you work on locally, as well as each of the branches in every remote associated with your local repo.

### Remote tracking branches

If you run `git branch --all` in your repository, you will notice a long list of branches. The branches that (by default) appear in red are the *remote tracking branches*. These branches are read-only copies of the branches on the remote. These update every time you run `git fetch` or `git pull`.

These don’t take up much room, so it’s okay that Git does this by default. But, these will stack up over time - they are not deleted automatically.

To delete the remote tracking branches that are deleted on the remote, run `git fetch --prune`. This is safe to do if you are using GitHub, because branches merged via pull requests can be restored.

### Local working branches

When you run `git branch --all`, you will also see the local working branches. These can be linked with branches on the remote, or they could exist with no remote counterpart.

-   `git clone [url]`: Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits.
-   `git status`: Always a good idea, this command shows you what branch you’re on, what files are in the working or staging directory, and any other important information.
-   `git push`: Uploads all local branch commits to the remote.
-   `git pull`: Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. `git pull` is a combination of `git fetch` and `git merge`.
