git-verify-tag(1) Manual Page
=============================

NAME
----

git-verify-tag - Check the GPG signature of tags

SYNOPSIS
--------

    git verify-tag [--format=<format>] <tag>…​

DESCRIPTION
-----------

Validates the gpg signature created by *git tag*.

OPTIONS
-------

--raw  
Print the raw gpg status output to standard error instead of the normal human-readable output.

-v  
--verbose  
Print the contents of the tag object before validating it.

&lt;tag&gt;…​  
SHA-1 identifiers of Git tag objects.

GIT
---
