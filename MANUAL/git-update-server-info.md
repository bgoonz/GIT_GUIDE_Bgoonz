git-update-server-info(1) Manual Page
=====================================

NAME
----

git-update-server-info - Update auxiliary info file to help dumb servers

SYNOPSIS
--------

    git update-server-info

DESCRIPTION
-----------

A dumb server that does not do on-the-fly pack generations must have some auxiliary information files in $GIT\_DIR/info and $GIT\_OBJECT\_DIRECTORY/info directories to help clients discover what references and packs the server has. This command generates such auxiliary files.

OUTPUT
------

Currently the command updates the following files. Please see [gitrepository-layout(5)](gitrepository-layout.html) for description of what they are for:

-   objects/info/packs

-   info/refs

GIT
---
