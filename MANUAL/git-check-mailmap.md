# git-check-mailmap(1) Manual Page

## NAME

git-check-mailmap - Show canonical names and email addresses of contacts

## SYNOPSIS

    git check-mailmap [<options>] <contact>…​

## DESCRIPTION

For each “Name &lt;user@host&gt;” or “&lt;user@host&gt;” from the command-line or standard input (when using `--stdin`), look up the person’s canonical name and email address (see "Mapping Authors" below). If found, print them; otherwise print the input as-is.

## OPTIONS

--stdin  
Read contacts, one per line, from the standard input after exhausting contacts provided on the command-line.

## OUTPUT

For each contact, a single line is output, terminated by a newline. If the name is provided or known to the _mailmap_, “Name &lt;user@host&gt;” is printed; otherwise only “&lt;user@host&gt;” is printed.

## CONFIGURATION

See `mailmap.file` and `mailmap.blob` in [git-config(1)](git-config.html) for how to specify a custom `.mailmap` target file or object.

## MAPPING AUTHORS

See [gitmailmap(5)](gitmailmap.html).

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
