git-sh-setup(1) Manual Page
===========================

NAME
----

git-sh-setup - Common Git shell script setup code

SYNOPSIS
--------

    . "$(git --exec-path)/git-sh-setup"

DESCRIPTION
-----------

This is not a command the end user would want to run. Ever. This documentation is meant for people who are studying the Porcelain-ish scripts and/or are writing new ones.

The *git sh-setup* scriptlet is designed to be sourced (using `.`) by other shell scripts to set up some variables pointing at the normal Git directories and a few helper shell functions.

Before sourcing it, your script should set up a few variables; `USAGE` (and `LONG_USAGE`, if any) is used to define message given by `usage()` shell function. `SUBDIRECTORY_OK` can be set if the script can run from a subdirectory of the working tree (some commands do not).

The scriptlet sets `GIT_DIR` and `GIT_OBJECT_DIRECTORY` shell variables, but does **not** export them to the environment.

FUNCTIONS
---------

die  
exit after emitting the supplied error message to the standard error stream.

usage  
die with the usage message.

set\_reflog\_action  
Set `GIT_REFLOG_ACTION` environment to a given string (typically the name of the program) unless it is already set. Whenever the script runs a `git` command that updates refs, a reflog entry is created using the value of this string to leave the record of what command updated the ref.

git\_editor  
runs an editor of user’s choice (GIT\_EDITOR, core.editor, VISUAL or EDITOR) on a given file, but error out if no editor is specified and the terminal is dumb.

is\_bare\_repository  
outputs `true` or `false` to the standard output stream to indicate if the repository is a bare repository (i.e. without an associated working tree).

cd\_to\_toplevel  
runs chdir to the toplevel of the working tree.

require\_work\_tree  
checks if the current directory is within the working tree of the repository, and otherwise dies.

require\_work\_tree\_exists  
checks if the working tree associated with the repository exists, and otherwise dies. Often done before calling cd\_to\_toplevel, which is impossible to do if there is no working tree.

 require\_clean\_work\_tree &lt;action&gt; \[&lt;hint&gt;\]   
checks that the working tree and index associated with the repository have no uncommitted changes to tracked files. Otherwise it emits an error message of the form `Cannot <action>: <reason>. <hint>`, and dies. Example:

    require_clean_work_tree rebase "Please commit or stash them."

get\_author\_ident\_from\_commit  
outputs code for use with eval to set the GIT\_AUTHOR\_NAME, GIT\_AUTHOR\_EMAIL and GIT\_AUTHOR\_DATE variables for a given commit.

create\_virtual\_base  
modifies the first file so only lines in common with the second file remain. If there is insufficient common material, then the first file is left empty. The result is suitable as a virtual base input for a 3-way merge.

GIT
---
