git-mergetool--lib(1) Manual Page
=================================

NAME
----

git-mergetool--lib - Common Git merge tool shell scriptlets

SYNOPSIS
--------

    TOOL_MODE=(diff|merge) . "$(git --exec-path)/git-mergetool--lib"

DESCRIPTION
-----------

This is not a command the end user would want to run. Ever. This documentation is meant for people who are studying the Porcelain-ish scripts and/or are writing new ones.

The *git-mergetool--lib* scriptlet is designed to be sourced (using `.`) by other shell scripts to set up functions for working with Git merge tools.

Before sourcing *git-mergetool--lib*, your script must set `TOOL_MODE` to define the operation mode for the functions listed below. *diff* and *merge* are valid values.

FUNCTIONS
---------

get\_merge\_tool  
returns a merge tool. the return code is 1 if we returned a guessed merge tool, else 0. *$GIT\_MERGETOOL\_GUI* may be set to *true* to search for the appropriate guitool.

get\_merge\_tool\_cmd  
returns the custom command for a merge tool.

get\_merge\_tool\_path  
returns the custom path for a merge tool.

initialize\_merge\_tool  
bring merge tool specific functions into scope so they can be used or overridden.

run\_merge\_tool  
launches a merge tool given the tool name and a true/false flag to indicate whether a merge base is present. *$MERGED*, *$LOCAL*, *$REMOTE*, and *$BASE* must be defined for use by the merge tool.

GIT
---

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
