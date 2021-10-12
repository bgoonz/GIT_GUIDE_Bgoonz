git-sh-i18n--envsubst(1) Manual Page
====================================

NAME
----

git-sh-i18n--envsubst - Git's own envsubst(1) for i18n fallbacks

SYNOPSIS
--------

    eval_gettext () {
            printf "%s" "$1" | (
                    export PATH $(git sh-i18n--envsubst --variables "$1");
                    git sh-i18n--envsubst "$1"
            )
    }

DESCRIPTION
-----------

This is not a command the end user would want to run. Ever. This documentation is meant for people who are studying the plumbing scripts and/or are writing new ones.

*git sh-i18n--envsubst* is Git’s stripped-down copy of the GNU `envsubst(1)` program that comes with the GNU gettext package. It’s used internally by [git-sh-i18n(1)](git-sh-i18n.html) to interpolate the variables passed to the `eval_gettext` function.

No promises are made about the interface, or that this program won’t disappear without warning in the next version of Git. Don’t use it.

GIT
---
