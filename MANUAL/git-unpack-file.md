git-unpack-file(1) Manual Page
==============================

NAME
----

git-unpack-file - Creates a temporary file with a blob's contents

SYNOPSIS
--------

    git unpack-file <blob>

DESCRIPTION
-----------

Creates a file holding the contents of the blob specified by sha1. It returns the name of the temporary file in the following format: .merge\_file\_XXXXX

OPTIONS
-------

&lt;blob&gt;  
Must be a blob id

GIT
---
