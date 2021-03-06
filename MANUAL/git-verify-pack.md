# git-verify-pack(1) Manual Page

## NAME

git-verify-pack - Validate packed Git archive files

## SYNOPSIS

    git verify-pack [-v|--verbose] [-s|--stat-only] [--] <pack>.idx …​

## DESCRIPTION

Reads given idx file for packed Git archive created with the _git pack-objects_ command and verifies idx file and the corresponding pack file.

## OPTIONS

&lt;pack&gt;.idx …​  
The idx files to verify.

-v  
--verbose  
After verifying the pack, show list of objects contained in the pack and a histogram of delta chain length.

-s  
--stat-only  
Do not verify the pack contents; only show the histogram of delta chain length. With `--verbose`, list of objects is also shown.

--  
Do not interpret any more arguments as options.

## OUTPUT FORMAT

When specifying the -v option the format used is:

    SHA-1 type size size-in-packfile offset-in-packfile

for objects that are not deltified in the pack, and

    SHA-1 type size size-in-packfile offset-in-packfile depth base-SHA-1

for objects that are deltified.

## GIT
