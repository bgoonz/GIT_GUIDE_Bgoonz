git-fmt-merge-msg(1) Manual Page
================================

NAME
----

git-fmt-merge-msg - Produce a merge commit message

SYNOPSIS
--------

    git fmt-merge-msg [-m <message>] [--log[=<n>] | --no-log]
    git fmt-merge-msg [-m <message>] [--log[=<n>] | --no-log] -F <file>

DESCRIPTION
-----------

Takes the list of merged objects on stdin and produces a suitable commit message to be used for the merge commit, usually to be passed as the *&lt;merge-message&gt;* argument of *git merge*.

This command is intended mostly for internal use by scripts automatically invoking *git merge*.

OPTIONS
-------

--log\[=&lt;n&gt;\]  
In addition to branch names, populate the log message with one-line descriptions from the actual commits that are being merged. At most &lt;n&gt; commits from each merge parent will be used (20 if &lt;n&gt; is omitted). This overrides the `merge.log` configuration variable.

--no-log  
Do not list one-line descriptions from the actual commits being merged.

--\[no-\]summary  
Synonyms to --log and --no-log; these are deprecated and will be removed in the future.

-m &lt;message&gt;  
--message &lt;message&gt;  
Use &lt;message&gt; instead of the branch names for the first line of the log message. For use with `--log`.

-F &lt;file&gt;  
--file &lt;file&gt;  
Take the list of merged objects from &lt;file&gt; instead of stdin.

CONFIGURATION
-------------

merge.branchdesc  
In addition to branch names, populate the log message with the branch description text associated with them. Defaults to false.

merge.log  
In addition to branch names, populate the log message with at most the specified number of one-line descriptions from the actual commits that are being merged. Defaults to false, and true is a synonym for 20.

merge.suppressDest  
By adding a glob that matches the names of integration branches to this multi-valued configuration variable, the default merge message computed for merges into these integration branches will omit "into &lt;branch name&gt;" from its title.

An element with an empty value can be used to clear the list of globs accumulated from previous configuration entries. When there is no `merge.suppressDest` variable defined, the default value of `master` is used for backward compatibility.

merge.summary  
Synonym to `merge.log`; this is deprecated and will be removed in the future.

EXAMPLES
--------

    $ git fetch origin master
    $ git fmt-merge-msg --log <$GIT_DIR/FETCH_HEAD

Print a log message describing a merge of the "master" branch from the "origin" remote.

SEE ALSO
--------

[git-merge(1)](git-merge.html)

GIT
---

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
