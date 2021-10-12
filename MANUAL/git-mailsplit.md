git-mailsplit(1) Manual Page
============================

NAME
----

git-mailsplit - Simple UNIX mbox splitter program

SYNOPSIS
--------

    git mailsplit [-b] [-f<nn>] [-d<prec>] [--keep-cr] [--mboxrd]
                    -o<directory> [--] [(<mbox>|<Maildir>)…​]

DESCRIPTION
-----------

Splits a mbox file or a Maildir into a list of files: "0001" "0002" .. in the specified directory so you can process them further from there.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><div class="title">Important</div></td><td>Maildir splitting relies upon filenames being sorted to output patches in the correct order.</td></tr></tbody></table>

OPTIONS
-------

&lt;mbox&gt;  
Mbox file to split. If not given, the mbox is read from the standard input.

&lt;Maildir&gt;  
Root of the Maildir to split. This directory should contain the cur, tmp and new subdirectories.

-o&lt;directory&gt;  
Directory in which to place the individual messages.

-b  
If any file doesn’t begin with a From line, assume it is a single mail message instead of signaling error.

-d&lt;prec&gt;  
Instead of the default 4 digits with leading zeros, different precision can be specified for the generated filenames.

-f&lt;nn&gt;  
Skip the first &lt;nn&gt; numbers, for example if -f3 is specified, start the numbering with 0004.

--keep-cr  
Do not remove `\r` from lines ending with `\r\n`.

--mboxrd  
Input is of the "mboxrd" format and "^&gt;+From " line escaping is reversed.

GIT
---

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
