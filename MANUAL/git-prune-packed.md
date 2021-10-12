# git-prune-packed(1) Manual Page

## NAME

git-prune-packed - Remove extra objects that are already in pack files

## SYNOPSIS

    git prune-packed [-n|--dry-run] [-q|--quiet]

## DESCRIPTION

This program searches the `$GIT_OBJECT_DIRECTORY` for all objects that currently exist in a pack file as well as the independent object directories.

All such extra objects are removed.

A pack is a collection of objects, individually compressed, with delta compression applied, stored in a single file, with an associated index file.

Packs are used to reduce the load on mirror systems, backup engines, disk storage, etc.

## OPTIONS

-n  
--dry-run  
Don’t actually remove any objects, only show those that would have been removed.

-q  
--quiet  
Squelch the progress indicator.

## SEE ALSO

[git-pack-objects(1)](git-pack-objects.html) [git-repack(1)](git-repack.html)

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
