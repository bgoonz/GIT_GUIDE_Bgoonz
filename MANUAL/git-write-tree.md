# git-write-tree(1) Manual Page

## NAME

git-write-tree - Create a tree object from the current index

## SYNOPSIS

    git write-tree [--missing-ok] [--prefix=<prefix>/]

## DESCRIPTION

Creates a tree object using the current index. The name of the new tree object is printed to standard output.

The index must be in a fully merged state.

Conceptually, _git write-tree_ sync()s the current index contents into a set of tree files. In order to have that match what is actually in your directory right now, you need to have done a _git update-index_ phase before you did the _git write-tree_.

## OPTIONS

--missing-ok  
Normally _git write-tree_ ensures that the objects referenced by the directory exist in the object database. This option disables this check.

--prefix=&lt;prefix&gt;/  
Writes a tree object that represents a subdirectory `<prefix>`. This can be used to write the tree object for a subproject that is in the named subdirectory.

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
