# git-sh-i18n(1) Manual Page

## NAME

git-sh-i18n - Git's i18n setup code for shell scripts

## SYNOPSIS

    . "$(git --exec-path)/git-sh-i18n"

## DESCRIPTION

This is not a command the end user would want to run. Ever. This documentation is meant for people who are studying the Porcelain-ish scripts and/or are writing new ones.

The 'git sh-i18n scriptlet is designed to be sourced (using `.`) by Git’s porcelain programs implemented in shell script. It provides wrappers for the GNU `gettext` and `eval_gettext` functions accessible through the `gettext.sh` script, and provides pass-through fallbacks on systems without GNU gettext.

## FUNCTIONS

gettext  
Currently a dummy fall-through function implemented as a wrapper around `printf(1)`. Will be replaced by a real gettext implementation in a later version.

eval_gettext  
Currently a dummy fall-through function implemented as a wrapper around `printf(1)` with variables expanded by the [git-sh-i18n--envsubst(1)](git-sh-i18n--envsubst.html) helper. Will be replaced by a real gettext implementation in a later version.

## GIT
