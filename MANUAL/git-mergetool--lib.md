# git-mergetool--lib(1) Manual Page

## NAME

git-mergetool--lib - Common Git merge tool shell scriptlets

## SYNOPSIS

    TOOL_MODE=(diff|merge) . "$(git --exec-path)/git-mergetool--lib"

## DESCRIPTION

This is not a command the end user would want to run. Ever. This documentation is meant for people who are studying the Porcelain-ish scripts and/or are writing new ones.

The _git-mergetool--lib_ scriptlet is designed to be sourced (using `.`) by other shell scripts to set up functions for working with Git merge tools.

Before sourcing _git-mergetool--lib_, your script must set `TOOL_MODE` to define the operation mode for the functions listed below. _diff_ and _merge_ are valid values.

## FUNCTIONS

get_merge_tool  
returns a merge tool. the return code is 1 if we returned a guessed merge tool, else 0. _$GIT_MERGETOOL_GUI_ may be set to _true_ to search for the appropriate guitool.

get_merge_tool_cmd  
returns the custom command for a merge tool.

get_merge_tool_path  
returns the custom path for a merge tool.

initialize_merge_tool  
bring merge tool specific functions into scope so they can be used or overridden.

run_merge_tool  
launches a merge tool given the tool name and a true/false flag to indicate whether a merge base is present. _$MERGED_, _$LOCAL_, _$REMOTE_, and _$BASE_ must be defined for use by the merge tool.

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
