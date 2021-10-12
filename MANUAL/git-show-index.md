git-show-index(1) Manual Page
=============================

NAME
----

git-show-index - Show packed archive index

SYNOPSIS
--------

    git show-index [--object-format=<hash-algorithm>]

DESCRIPTION
-----------

Read the `.idx` file for a Git packfile (created with [git-pack-objects(1)](git-pack-objects.html) or [git-index-pack(1)](git-index-pack.html)) from the standard input, and dump its contents. The output consists of one object per line, with each line containing two or three space-separated columns:

-   the first column is the offset in bytes of the object within the corresponding packfile

-   the second column is the object id of the object

-   if the index version is 2 or higher, the third column contains the CRC32 of the object data

The objects are output in the order in which they are found in the index file, which should be (in a correctly constructed file) sorted by object id.

Note that you can get more information on a packfile by calling [git-verify-pack(1)](git-verify-pack.html). However, as this command considers only the index file itself, it’s both faster and more flexible.

OPTIONS
-------

--object-format=&lt;hash-algorithm&gt;  
Specify the given object format (hash algorithm) for the index file. The valid values are *sha1* and (if enabled) *sha256*. The default is the algorithm for the current repository (set by `extensions.objectFormat`), or *sha1* if no value is set or outside a repository..

THIS OPTION IS EXPERIMENTAL! SHA-256 support is experimental and still in an early stage. A SHA-256 repository will in general not be able to share work with "regular" SHA-1 repositories. It should be assumed that, e.g., Git internal file formats in relation to SHA-256 repositories may change in backwards-incompatible ways. Only use `--object-format=sha256` for testing purposes.

GIT
---
