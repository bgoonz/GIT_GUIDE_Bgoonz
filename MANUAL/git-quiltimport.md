# git-quiltimport(1) Manual Page

## NAME

git-quiltimport - Applies a quilt patchset onto the current branch

## SYNOPSIS

    git quiltimport [--dry-run | -n] [--author <author>] [--patches <dir>]
                    [--series <file>] [--keep-non-patch]

## DESCRIPTION

Applies a quilt patchset onto the current Git branch, preserving the patch boundaries, patch order, and patch descriptions present in the quilt patchset.

For each patch the code attempts to extract the author from the patch description. If that fails it falls back to the author specified with --author. If the --author flag was not given the patch description is displayed and the user is asked to interactively enter the author of the patch.

If a subject is not found in the patch description the patch name is preserved as the 1 line subject in the Git description.

## OPTIONS

-n  
--dry-run  
Walk through the patches in the series and warn if we cannot find all of the necessary information to commit a patch. At the time of this writing only missing author information is warned about.

--author Author Name &lt;Author Email&gt;  
The author name and email address to use when no author information can be found in the patch description.

--patches &lt;dir&gt;  
The directory to find the quilt patches.

The default for the patch directory is patches or the value of the `$QUILT_PATCHES` environment variable.

--series &lt;file&gt;  
The quilt series file.

The default for the series file is &lt;patches&gt;/series or the value of the `$QUILT_SERIES` environment variable.

--keep-non-patch  
Pass `-b` flag to _git mailinfo_ (see [git-mailinfo(1)](git-mailinfo.html)).

## GIT
