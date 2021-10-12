# git-mailinfo(1) Manual Page

## NAME

git-mailinfo - Extracts patch and authorship from a single e-mail message

## SYNOPSIS

    git mailinfo [-k|-b] [-u | --encoding=<encoding> | -n] [--[no-]scissors] <msg> <patch>

## DESCRIPTION

Reads a single e-mail message from the standard input, and writes the commit log message in &lt;msg&gt; file, and the patches in &lt;patch&gt; file. The author name, e-mail and e-mail subject are written out to the standard output to be used by _git am_ to create a commit. It is usually not necessary to use this command directly. See [git-am(1)](git-am.html) instead.

## OPTIONS

-k  
Usually the program removes email cruft from the Subject: header line to extract the title line for the commit log message. This option prevents this munging, and is most useful when used to read back _git format-patch -k_ output.

Specifically, the following are removed until none of them remain:

- Leading and trailing whitespace.

- Leading `Re:`, `re:`, and `:`.

- Leading bracketed strings (between `[` and `]`, usually `[PATCH]`).

Finally, runs of whitespace are normalized to a single ASCII space character.

-b  
When -k is not in effect, all leading strings bracketed with _\[_ and _\]_ pairs are stripped. This option limits the stripping to only the pairs whose bracketed string contains the word "PATCH".

-u  
The commit log message, author name and author email are taken from the e-mail, and after minimally decoding MIME transfer encoding, re-coded in the charset specified by `i18n.commitEncoding` (defaulting to UTF-8) by transliterating them. This used to be optional but now it is the default.

Note that the patch is always used as-is without charset conversion, even with this flag.

--encoding=&lt;encoding&gt;  
Similar to -u. But when re-coding, the charset specified here is used instead of the one specified by `i18n.commitEncoding` or UTF-8.

-n  
Disable all charset re-coding of the metadata.

-m  
--message-id  
Copy the Message-ID header at the end of the commit message. This is useful in order to associate commits with mailing list discussions.

--scissors  
Remove everything in body before a scissors line (e.g. "-- &gt;8 --"). The line represents scissors and perforation marks, and is used to request the reader to cut the message at that line. If that line appears in the body of the message before the patch, everything before it (including the scissors line itself) is ignored when this option is used.

This is useful if you want to begin your message in a discussion thread with comments and suggestions on the message you are responding to, and to conclude it with a patch submission, separating the discussion and the beginning of the proposed commit log message with a scissors line.

This can be enabled by default with the configuration option mailinfo.scissors.

--no-scissors  
Ignore scissors lines. Useful for overriding mailinfo.scissors settings.

&lt;msg&gt;  
The commit log message extracted from e-mail, usually except the title line which comes from e-mail Subject.

&lt;patch&gt;  
The patch extracted from e-mail.

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
