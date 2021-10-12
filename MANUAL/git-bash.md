git-bash(1) Manual Page
=======================

NAME
----

git-bash - A Windows-specific wrapper to open a Git Bash window

SYNOPSIS
--------

    git-bash [--cd-to-home] [--cd=<directory>] [--minimal-search-path]
        [--command=<path>] [--app-id=<id>] [<args>…​]

DESCRIPTION
-----------

This command opens a window with an interactive Git Bash. It is specific to the Git for Windows project.

By default, this will open a MinTTY window, but it can be configured in Git for Windows' installer to use Windows' default Console window instead.

Before starting the interactive Bash session, the environment is adjusted a bit. For example, the `PATH` is adjusted to find the `git` executable, and `git-bash` will ensure that `HOME` is set (because it is expected to be present by Git, and to point to the current user’s home directory). See the [ENVIRONMENT VARIABLES](#ENVIRONMENT-VARIABLES) section below for more information.

OPTIONS
-------

--cd-to-home  
--no-cd  
--cd=&lt;directory&gt;  
By default, Git Bash will not change the current directory; To allow e.g. for Windows Explorer integration ("Git Bash Here"), the `--cd=<directory>` option can be used to change the current directory before running the interactive Bash.

The `--cd-to-home` option can be used to change the current directory to the user’s home directory (as determined by the environment variable `HOME`). The `--no-cd` option can be used to override `--cd` options that precede it.

--minimal-search-path  
--no-minimal-search-path  
By default, Git Bash will adjust the `PATH` not only to include the `git` executable, but also all of the Unix-y tools (such as `sed`, `awk`, etc). With `--minimal-search-path`, it will be adjusted so that **only** the `git`, `git-gui` and `gitk` executables are found, as well as the scripts `start-ssh-agent.cmd` and `start-ssh-pageant.cmd`.

--command=&lt;command&gt;  
Allows the user to ask for a different command to be specified. Defaults to `usr\\bin\\mintty.exe`. If the specified command is not an absolute path, it is interpreted relative to `git-bash.exe`.

--app-id=&lt;command&gt;  
Allows the user to override the ID used e.g. in Windows' Task Bar. Defaults to `GitForWindows.Bash`.

--needs-console  
--no-needs-console  
--hide  
--no-hide  
--append-quote  
--no-append-quote  
These options do not make sense in the context of `git-bash`; They are merely inherited from the Git Wrapper (see the [GIT WRAPPER](#GIT-WRAPPER) section below).

### ENVIRONMENT VARIABLES

Upon startup, `git-bash` will ensure that a couple of environment variables are set/adjusted.

The most important variable to adjust is `PATH`: Git Bash does want to make sure that the `git` executable is in the search path.

If `HOME` is unset, `git-bash` will first look whether `%HOMEDRIVE%%HOMEPATH%` points to a valid directory and if it does, use it as value for `HOME`. If either `HOMEDRIVE` or `HOMEPATH` are unset, or if they do not point to a valid directory, `%USERPROFILE%` is used instead.

### GIT WRAPPER

In the Git for Windows project, the source code of `git-bash` is called the "Git Wrapper", as it merely parses the command-line parameters, sets up a few environment variables, then spawns the actual command, and waits for the spawned command to exit. The Git Wrapper is not only used for `git-bash` but also for `git-cmd` and for certain placeholders internal to Git (the so-called "built-ins").

GIT
---
