git-replace(1) Manual Page
==========================

NAME
----

git-replace - Create, list, delete refs to replace objects

SYNOPSIS
--------

    git replace [-f] <object> <replacement>
    git replace [-f] --edit <object>
    git replace [-f] --graft <commit> [<parent>…​]
    git replace [-f] --convert-graft-file
    git replace -d <object>…​
    git replace [--format=<format>] [-l [<pattern>]]

DESCRIPTION
-----------

Adds a *replace* reference in `refs/replace/` namespace.

The name of the *replace* reference is the SHA-1 of the object that is replaced. The content of the *replace* reference is the SHA-1 of the replacement object.

The replaced object and the replacement object must be of the same type. This restriction can be bypassed using `-f`.

Unless `-f` is given, the *replace* reference must not yet exist.

There is no other restriction on the replaced and replacement objects. Merge commits can be replaced by non-merge commits and vice versa.

Replacement references will be used by default by all Git commands except those doing reachability traversal (prune, pack transfer and fsck).

It is possible to disable use of replacement references for any command using the `--no-replace-objects` option just after *git*.

For example if commit *foo* has been replaced by commit *bar*:

    $ git --no-replace-objects cat-file commit foo

shows information about commit *foo*, while:

    $ git cat-file commit foo

shows information about commit *bar*.

The `GIT_NO_REPLACE_OBJECTS` environment variable can be set to achieve the same effect as the `--no-replace-objects` option.

OPTIONS
-------

-f  
--force  
If an existing replace ref for the same object exists, it will be overwritten (instead of failing).

-d  
--delete  
Delete existing replace refs for the given objects.

--edit &lt;object&gt;  
Edit an object’s content interactively. The existing content for &lt;object&gt; is pretty-printed into a temporary file, an editor is launched on the file, and the result is parsed to create a new object of the same type as &lt;object&gt;. A replacement ref is then created to replace &lt;object&gt; with the newly created object. See [git-var(1)](git-var.html) for details about how the editor will be chosen.

--raw  
When editing, provide the raw object contents rather than pretty-printed ones. Currently this only affects trees, which will be shown in their binary form. This is harder to work with, but can help when repairing a tree that is so corrupted it cannot be pretty-printed. Note that you may need to configure your editor to cleanly read and write binary data.

--graft &lt;commit&gt; \[&lt;parent&gt;…​\]  
Create a graft commit. A new commit is created with the same content as &lt;commit&gt; except that its parents will be \[&lt;parent&gt;…​\] instead of &lt;commit&gt;'s parents. A replacement ref is then created to replace &lt;commit&gt; with the newly created commit. Use `--convert-graft-file` to convert a `$GIT_DIR/info/grafts` file and use replace refs instead.

--convert-graft-file  
Creates graft commits for all entries in `$GIT_DIR/info/grafts` and deletes that file upon success. The purpose is to help users with transitioning off of the now-deprecated graft file.

-l &lt;pattern&gt;  
--list &lt;pattern&gt;  
List replace refs for objects that match the given pattern (or all if no pattern is given). Typing "git replace" without arguments, also lists all replace refs.

--format=&lt;format&gt;  
When listing, use the specified &lt;format&gt;, which can be one of *short*, *medium* and *long*. When omitted, the format defaults to *short*.

FORMATS
-------

The following format are available:

-   *short*: &lt;replaced sha1&gt;

-   *medium*: &lt;replaced sha1&gt; → &lt;replacement sha1&gt;

-   *long*: &lt;replaced sha1&gt; (&lt;replaced type&gt;) → &lt;replacement sha1&gt; (&lt;replacement type&gt;)

CREATING REPLACEMENT OBJECTS
----------------------------

[git-hash-object(1)](git-hash-object.html), [git-rebase(1)](git-rebase.html), and [git-filter-repo](https://github.com/newren/git-filter-repo), among other git commands, can be used to create replacement objects from existing objects. The `--edit` option can also be used with *git replace* to create a replacement object by editing an existing object.

If you want to replace many blobs, trees or commits that are part of a string of commits, you may just want to create a replacement string of commits and then only replace the commit at the tip of the target string of commits with the commit at the tip of the replacement string of commits.

BUGS
----

Comparing blobs or trees that have been replaced with those that replace them will not work properly. And using `git reset --hard` to go back to a replaced commit will move the branch to the replacement commit instead of the replaced commit.

There may be other problems when using *git rev-list* related to pending objects.

SEE ALSO
--------

[git-hash-object(1)](git-hash-object.html) [git-rebase(1)](git-rebase.html) [git-tag(1)](git-tag.html) [git-branch(1)](git-branch.html) [git-commit(1)](git-commit.html) [git-var(1)](git-var.html) [git(1)](git.html) [git-filter-repo](https://github.com/newren/git-filter-repo)

GIT
---

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
