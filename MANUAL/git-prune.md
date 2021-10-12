# git-prune(1) Manual Page

## NAME

git-prune - Prune all unreachable objects from the object database

## SYNOPSIS

    git prune [-n] [-v] [--progress] [--expire <time>] [--] [<head>…​]

## DESCRIPTION

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><div class="title">Note</div></td><td>In most cases, users should run <em>git gc</em>, which calls <em>git prune</em>. See the section "NOTES", below.</td></tr></tbody></table>

This runs _git fsck --unreachable_ using all the refs available in `refs/`, optionally with additional set of objects specified on the command line, and prunes all unpacked objects unreachable from any of these head objects from the object database. In addition, it prunes the unpacked objects that are also found in packs by running _git prune-packed_. It also removes entries from .git/shallow that are not reachable by any ref.

Note that unreachable, packed objects will remain. If this is not desired, see [git-repack(1)](git-repack.html).

## OPTIONS

-n  
--dry-run  
Do not remove anything; just report what it would remove.

-v  
--verbose  
Report all removed objects.

--progress  
Show progress.

--expire &lt;time&gt;  
Only expire loose objects older than &lt;time&gt;.

--  
Do not interpret any more arguments as options.

&lt;head&gt;…​  
In addition to objects reachable from any of our references, keep objects reachable from listed &lt;head&gt;s.

## EXAMPLES

To prune objects not used by your repository or another that borrows from your repository via its `.git/objects/info/alternates`:

    $ git prune $(cd ../another && git rev-parse --all)

## NOTES

In most cases, users will not need to call _git prune_ directly, but should instead call _git gc_, which handles pruning along with many other housekeeping tasks.

For a description of which objects are considered for pruning, see _git fsck_'s --unreachable option.

## SEE ALSO

[git-fsck(1)](git-fsck.html), [git-gc(1)](git-gc.html), [git-reflog(1)](git-reflog.html)

## GIT
