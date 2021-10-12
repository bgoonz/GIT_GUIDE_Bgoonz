# git-stripspace(1) Manual Page

## NAME

git-stripspace - Remove unnecessary whitespace

## SYNOPSIS

    git stripspace [-s | --strip-comments]
    git stripspace [-c | --comment-lines]

## DESCRIPTION

Read text, such as commit messages, notes, tags and branch descriptions, from the standard input and clean it in the manner used by Git.

With no arguments, this will:

- remove trailing whitespace from all lines

- collapse multiple consecutive empty lines into one empty line

- remove empty lines from the beginning and end of the input

- add a missing _\\n_ to the last line if necessary.

In the case where the input consists entirely of whitespace characters, no output will be produced.

**NOTE**: This is intended for cleaning metadata, prefer the `--whitespace=fix` mode of [git-apply(1)](git-apply.html) for correcting whitespace of patches or files in the repository.

## OPTIONS

-s  
--strip-comments  
Skip and remove all lines starting with comment character (default _\#_).

-c  
--comment-lines  
Prepend comment character and blank to each line. Lines will automatically be terminated with a newline. On empty lines, only the comment character will be prepended.

## EXAMPLES

Given the following noisy input with _$_ indicating the end of a line:

    |A brief introduction   $
    |   $
    |$
    |A new paragraph$
    |# with a commented-out line    $
    |explaining lots of stuff.$
    |$
    |# An old paragraph, also commented-out. $
    |      $
    |The end.$
    |  $

Use _git stripspace_ with no arguments to obtain:

    |A brief introduction$
    |$
    |A new paragraph$
    |# with a commented-out line$
    |explaining lots of stuff.$
    |$
    |# An old paragraph, also commented-out.$
    |$
    |The end.$

Use _git stripspace --strip-comments_ to obtain:

    |A brief introduction$
    |$
    |A new paragraph$
    |explaining lots of stuff.$
    |$
    |The end.$

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
