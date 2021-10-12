git-ls-tree(1) Manual Page
==========================

NAME
----

git-ls-tree - List the contents of a tree object

SYNOPSIS
--------

    git ls-tree [-d] [-r] [-t] [-l] [-z]
                [--name-only] [--name-status] [--full-name] [--full-tree] [--abbrev[=<n>]]
                <tree-ish> [<path>…​]

DESCRIPTION
-----------

Lists the contents of a given tree object, like what "/bin/ls -a" does in the current working directory. Note that:

-   the behaviour is slightly different from that of "/bin/ls" in that the *&lt;path&gt;* denotes just a list of patterns to match, e.g. so specifying directory name (without `-r`) will behave differently, and order of the arguments does not matter.

-   the behaviour is similar to that of "/bin/ls" in that the *&lt;path&gt;* is taken as relative to the current working directory. E.g. when you are in a directory *sub* that has a directory *dir*, you can run *git ls-tree -r HEAD dir* to list the contents of the tree (that is `sub/dir` in `HEAD`). You don’t want to give a tree that is not at the root level (e.g. `git ls-tree -r HEAD:sub dir`) in this case, as that would result in asking for `sub/sub/dir` in the `HEAD` commit. However, the current working directory can be ignored by passing --full-tree option.

OPTIONS
-------

&lt;tree-ish&gt;  
Id of a tree-ish.

-d  
Show only the named tree entry itself, not its children.

-r  
Recurse into sub-trees.

-t  
Show tree entries even when going to recurse them. Has no effect if `-r` was not passed. `-d` implies `-t`.

-l  
--long  
Show object size of blob (file) entries.

-z  
\\0 line termination on output and do not quote filenames. See OUTPUT FORMAT below for more information.

--name-only  
--name-status  
List only filenames (instead of the "long" output), one per line.

--abbrev\[=&lt;n&gt;\]  
Instead of showing the full 40-byte hexadecimal object lines, show the shortest prefix that is at least *&lt;n&gt;* hexdigits long that uniquely refers the object. Non default number of digits can be specified with --abbrev=&lt;n&gt;.

--full-name  
Instead of showing the path names relative to the current working directory, show the full path names.

--full-tree  
Do not limit the listing to the current working directory. Implies --full-name.

\[&lt;path&gt;…​\]  
When paths are given, show them (note that this isn’t really raw pathnames, but rather a list of patterns to match). Otherwise implicitly uses the root level of the tree as the sole path argument.

Output Format
-------------

    <mode> SP <type> SP <object> TAB <file>

This output format is compatible with what `--index-info --stdin` of *git update-index* expects.

When the `-l` option is used, format changes to

    <mode> SP <type> SP <object> SP <object size> TAB <file>

Object size identified by &lt;object&gt; is given in bytes, and right-justified with minimum width of 7 characters. Object size is given only for blobs (file) entries; for other entries `-` character is used in place of size.

Without the `-z` option, pathnames with "unusual" characters are quoted as explained for the configuration variable `core.quotePath` (see [git-config(1)](git-config.html)). Using `-z` the filename is output verbatim and the line is terminated by a NUL byte.

GIT
---

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
