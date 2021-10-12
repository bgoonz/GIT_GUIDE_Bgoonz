# git-verify-commit(1) Manual Page

## NAME

git-verify-commit - Check the GPG signature of commits

## SYNOPSIS

    git verify-commit <commit>…​

## DESCRIPTION

Validates the GPG signature created by _git commit -S_.

## OPTIONS

--raw  
Print the raw gpg status output to standard error instead of the normal human-readable output.

-v  
--verbose  
Print the contents of the commit object before validating it.

&lt;commit&gt;…​  
SHA-1 identifiers of Git commit objects.

## GIT
