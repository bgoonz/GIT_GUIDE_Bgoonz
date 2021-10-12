# git-get-tar-commit-id(1) Manual Page

## NAME

git-get-tar-commit-id - Extract commit ID from an archive created using git-archive

## SYNOPSIS

    git get-tar-commit-id

## DESCRIPTION

Read a tar archive created by _git archive_ from the standard input and extract the commit ID stored in it. It reads only the first 1024 bytes of input, thus its runtime is not influenced by the size of the tar archive very much.

If no commit ID is found, _git get-tar-commit-id_ quietly exists with a return code of 1. This can happen if the archive had not been created using _git archive_ or if the first parameter of _git archive_ had been a tree ID instead of a commit ID or tag.

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
