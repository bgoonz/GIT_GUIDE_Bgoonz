# git-update-server-info(1) Manual Page

## NAME

git-update-server-info - Update auxiliary info file to help dumb servers

## SYNOPSIS

    git update-server-info

## DESCRIPTION

A dumb server that does not do on-the-fly pack generations must have some auxiliary information files in $GIT_DIR/info and $GIT_OBJECT_DIRECTORY/info directories to help clients discover what references and packs the server has. This command generates such auxiliary files.

## OUTPUT

Currently the command updates the following files. Please see [gitrepository-layout(5)](gitrepository-layout.html) for description of what they are for:

- objects/info/packs

- info/refs

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
