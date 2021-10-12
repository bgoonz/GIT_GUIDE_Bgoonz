# gitrevisions(7) Manual Page

## NAME

gitrevisions - Specifying revisions and ranges for Git

## SYNOPSIS

gitrevisions

## DESCRIPTION

Many Git commands take revision parameters as arguments. Depending on the command, they denote a specific commit or, for commands which walk the revision graph (such as [git-log(1)](git-log.html)), all commits which are reachable from that commit. For commands that walk the revision graph one can also specify a range of revisions explicitly.

In addition, some Git commands (such as [git-show(1)](git-show.html) and [git-push(1)](git-push.html)) can also take revision parameters which denote other objects than commits, e.g. blobs ("files") or trees ("directories of files").

## SPECIFYING REVISIONS

A revision parameter _&lt;rev&gt;_ typically, but not necessarily, names a commit object. It uses what is called an _extended SHA-1_ syntax. Here are various ways to spell object names. The ones listed near the end of this list name trees and blobs contained in a commit.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><div class="title">Note</div></td><td>This document shows the "raw" syntax as seen by git. The shell and other UIs might require additional quoting to protect special characters and to avoid word splitting.</td></tr></tbody></table>

_&lt;sha1&gt;_, e.g. _dae86e1950b1277e545cee180551750029cfe735_, _dae86e_  
The full SHA-1 object name (40-byte hexadecimal string), or a leading substring that is unique within the repository. E.g. dae86e1950b1277e545cee180551750029cfe735 and dae86e both name the same commit object if there is no other object in your repository whose object name starts with dae86e.

_&lt;describeOutput&gt;_, e.g. _v1.7.4.2-679-g3bee7fb_  
Output from `git describe`; i.e. a closest tag, optionally followed by a dash and a number of commits, followed by a dash, a _g_, and an abbreviated object name.

_&lt;refname&gt;_, e.g. _master_, _heads/master_, _refs/heads/master_  
A symbolic ref name. E.g. _master_ typically means the commit object referenced by _refs/heads/master_. If you happen to have both _heads/master_ and _tags/master_, you can explicitly say _heads/master_ to tell Git which one you mean. When ambiguous, a _&lt;refname&gt;_ is disambiguated by taking the first match in the following rules:

1.  If _$GIT_DIR/&lt;refname&gt;_ exists, that is what you mean (this is usually useful only for `HEAD`, `FETCH_HEAD`, `ORIG_HEAD`, `MERGE_HEAD` and `CHERRY_PICK_HEAD`);

2.  otherwise, _refs/&lt;refname&gt;_ if it exists;

3.  otherwise, _refs/tags/&lt;refname&gt;_ if it exists;

4.  otherwise, _refs/heads/&lt;refname&gt;_ if it exists;

5.  otherwise, _refs/remotes/&lt;refname&gt;_ if it exists;

6.  otherwise, _refs/remotes/&lt;refname&gt;/HEAD_ if it exists.

    `HEAD` names the commit on which you based the changes in the working tree. `FETCH_HEAD` records the branch which you fetched from a remote repository with your last `git fetch` invocation. `ORIG_HEAD` is created by commands that move your `HEAD` in a drastic way, to record the position of the `HEAD` before their operation, so that you can easily change the tip of the branch back to the state before you ran them. `MERGE_HEAD` records the commit(s) which you are merging into your branch when you run `git merge`. `CHERRY_PICK_HEAD` records the commit which you are cherry-picking when you run `git cherry-pick`.

    Note that any of the \*refs/\*\* cases above may come either from the `$GIT_DIR/refs` directory or from the `$GIT_DIR/packed-refs` file. While the ref name encoding is unspecified, UTF-8 is preferred as some output processing may assume ref names in UTF-8.

_@_  
_@_ alone is a shortcut for `HEAD`.

_\[&lt;refname&gt;\]@{&lt;date&gt;}_, e.g. _master@{yesterday}_, _HEAD@{5 minutes ago}_  
A ref followed by the suffix _@_ with a date specification enclosed in a brace pair (e.g. _{yesterday}_, _{1 month 2 weeks 3 days 1 hour 1 second ago}_ or _{1979-02-26 18:30:00}_) specifies the value of the ref at a prior point in time. This suffix may only be used immediately following a ref name and the ref must have an existing log (_$GIT_DIR/logs/&lt;ref&gt;_). Note that this looks up the state of your **local** ref at a given time; e.g., what was in your local _master_ branch last week. If you want to look at commits made during certain times, see `--since` and `--until`.

_&lt;refname&gt;@{&lt;n&gt;}_, e.g. _master@{1}_  
A ref followed by the suffix _@_ with an ordinal specification enclosed in a brace pair (e.g. _{1}_, _{15}_) specifies the n-th prior value of that ref. For example _master@{1}_ is the immediate prior value of _master_ while _master@{5}_ is the 5th prior value of _master_. This suffix may only be used immediately following a ref name and the ref must have an existing log (_$GIT_DIR/logs/&lt;refname&gt;_).

_@{&lt;n&gt;}_, e.g. _@{1}_  
You can use the _@_ construct with an empty ref part to get at a reflog entry of the current branch. For example, if you are on branch _blabla_ then _@{1}_ means the same as _blabla@{1}_.

_@{-&lt;n&gt;}_, e.g. _@{-1}_  
The construct _@{-&lt;n&gt;}_ means the &lt;n&gt;th branch/commit checked out before the current one.

_\[&lt;branchname&gt;\]@{upstream}_, e.g. _master@{upstream}_, _@{u}_  
The suffix _@{upstream}_ to a branchname (short form _&lt;branchname&gt;@{u}_) refers to the branch that the branch specified by branchname is set to build on top of (configured with `branch.<name>.remote` and `branch.<name>.merge`). A missing branchname defaults to the current one. These suffixes are also accepted when spelled in uppercase, and they mean the same thing no matter the case.

_\[&lt;branchname&gt;\]@{push}_, e.g. _master@{push}_, _@{push}_  
The suffix _@{push}_ reports the branch "where we would push to" if `git push` were run while `branchname` was checked out (or the current `HEAD` if no branchname is specified). Since our push destination is in a remote repository, of course, we report the local tracking branch that corresponds to that branch (i.e., something in `refs/remotes/`).

Here’s an example to make it more clear:

    $ git config push.default current
    $ git config remote.pushdefault myfork
    $ git switch -c mybranch origin/master

    $ git rev-parse --symbolic-full-name @{upstream}
    refs/remotes/origin/master

    $ git rev-parse --symbolic-full-name @{push}
    refs/remotes/myfork/mybranch

Note in the example that we set up a triangular workflow, where we pull from one location and push to another. In a non-triangular workflow, _@{push}_ is the same as _@{upstream}_, and there is no need for it.

This suffix is also accepted when spelled in uppercase, and means the same thing no matter the case.

_&lt;rev&gt;^\[&lt;n&gt;\]_, e.g. _HEAD^, v1.5.1^0_  
A suffix _^_ to a revision parameter means the first parent of that commit object. _^&lt;n&gt;_ means the &lt;n&gt;th parent (i.e. _&lt;rev&gt;^_ is equivalent to _&lt;rev&gt;^1_). As a special rule, _&lt;rev&gt;^0_ means the commit itself and is used when _&lt;rev&gt;_ is the object name of a tag object that refers to a commit object.

_&lt;rev&gt;~\[&lt;n&gt;\]_, e.g. _HEAD~, master~3_  
A suffix _~_ to a revision parameter means the first parent of that commit object. A suffix _~&lt;n&gt;_ to a revision parameter means the commit object that is the &lt;n&gt;th generation ancestor of the named commit object, following only the first parents. I.e. _&lt;rev&gt;~3_ is equivalent to _&lt;rev&gt;^^^_ which is equivalent to _&lt;rev&gt;^1^1^1_. See below for an illustration of the usage of this form.

_&lt;rev&gt;^{&lt;type&gt;}_, e.g. _v0.99.8^{commit}_  
A suffix _^_ followed by an object type name enclosed in brace pair means dereference the object at _&lt;rev&gt;_ recursively until an object of type _&lt;type&gt;_ is found or the object cannot be dereferenced anymore (in which case, barf). For example, if _&lt;rev&gt;_ is a commit-ish, _&lt;rev&gt;^{commit}_ describes the corresponding commit object. Similarly, if _&lt;rev&gt;_ is a tree-ish, _&lt;rev&gt;^{tree}_ describes the corresponding tree object. _&lt;rev&gt;^0_ is a short-hand for _&lt;rev&gt;^{commit}_.

_&lt;rev&gt;^{object}_ can be used to make sure _&lt;rev&gt;_ names an object that exists, without requiring _&lt;rev&gt;_ to be a tag, and without dereferencing _&lt;rev&gt;_; because a tag is already an object, it does not have to be dereferenced even once to get to an object.

_&lt;rev&gt;^{tag}_ can be used to ensure that _&lt;rev&gt;_ identifies an existing tag object.

_&lt;rev&gt;^{}_, e.g. _v0.99.8^{}_  
A suffix _^_ followed by an empty brace pair means the object could be a tag, and dereference the tag recursively until a non-tag object is found.

_&lt;rev&gt;^{/&lt;text&gt;}_, e.g. _HEAD^{/fix nasty bug}_  
A suffix _^_ to a revision parameter, followed by a brace pair that contains a text led by a slash, is the same as the _:/fix nasty bug_ syntax below except that it returns the youngest matching commit which is reachable from the _&lt;rev&gt;_ before _^_.

_:/&lt;text&gt;_, e.g. _:/fix nasty bug_  
A colon, followed by a slash, followed by a text, names a commit whose commit message matches the specified regular expression. This name returns the youngest matching commit which is reachable from any ref, including HEAD. The regular expression can match any part of the commit message. To match messages starting with a string, one can use e.g. _:/^foo_. The special sequence _:/!_ is reserved for modifiers to what is matched. _:/!-foo_ performs a negative match, while _:/!!foo_ matches a literal _!_ character, followed by _foo_. Any other sequence beginning with _:/!_ is reserved for now. Depending on the given text, the shell’s word splitting rules might require additional quoting.

_&lt;rev&gt;:&lt;path&gt;_, e.g. _HEAD:README_, _master:./README_  
A suffix _:_ followed by a path names the blob or tree at the given path in the tree-ish object named by the part before the colon. A path starting with _./_ or _../_ is relative to the current working directory. The given path will be converted to be relative to the working tree’s root directory. This is most useful to address a blob or tree from a commit or tree that has the same tree structure as the working tree.

_:\[&lt;n&gt;:\]&lt;path&gt;_, e.g. _:0:README_, _:README_  
A colon, optionally followed by a stage number (0 to 3) and a colon, followed by a path, names a blob object in the index at the given path. A missing stage number (and the colon that follows it) names a stage 0 entry. During a merge, stage 1 is the common ancestor, stage 2 is the target branch’s version (typically the current branch), and stage 3 is the version from the branch which is being merged.

Here is an illustration, by Jon Loeliger. Both commit nodes B and C are parents of commit node A. Parent commits are ordered left-to-right.

    G   H   I   J
     \ /     \ /
      D   E   F
       \  |  / \
        \ | /   |
         \|/    |
          B     C
           \   /
            \ /
             A

    A =      = A^0
    B = A^   = A^1     = A~1
    C =      = A^2
    D = A^^  = A^1^1   = A~2
    E = B^2  = A^^2
    F = B^3  = A^^3
    G = A^^^ = A^1^1^1 = A~3
    H = D^2  = B^^2    = A^^^2  = A~2^2
    I = F^   = B^3^    = A^^3^
    J = F^2  = B^3^2   = A^^3^2

## SPECIFYING RANGES

History traversing commands such as `git log` operate on a set of commits, not just a single commit.

For these commands, specifying a single revision, using the notation described in the previous section, means the set of commits `reachable` from the given commit.

Specifying several revisions means the set of commits reachable from any of the given commits.

A commit’s reachable set is the commit itself and the commits in its ancestry chain.

### Commit Exclusions

_^&lt;rev&gt;_ (caret) Notation  
To exclude commits reachable from a commit, a prefix _^_ notation is used. E.g. _^r1 r2_ means commits reachable from _r2_ but exclude the ones reachable from _r1_ (i.e. _r1_ and its ancestors).

### Dotted Range Notations

The _.._ (two-dot) Range Notation  
The _^r1 r2_ set operation appears so often that there is a shorthand for it. When you have two commits _r1_ and _r2_ (named according to the syntax explained in SPECIFYING REVISIONS above), you can ask for commits that are reachable from r2 excluding those that are reachable from r1 by _^r1 r2_ and it can be written as _r1..r2_.

The _…​_ (three-dot) Symmetric Difference Notation  
A similar notation _r1...r2_ is called symmetric difference of _r1_ and _r2_ and is defined as _r1 r2 --not $(git merge-base --all r1 r2)_. It is the set of commits that are reachable from either one of _r1_ (left side) or _r2_ (right side) but not from both.

In these two shorthand notations, you can omit one end and let it default to HEAD. For example, _origin.._ is a shorthand for _origin..HEAD_ and asks "What did I do since I forked from the origin branch?" Similarly, _..origin_ is a shorthand for _HEAD..origin_ and asks "What did the origin do since I forked from them?" Note that _.._ would mean _HEAD..HEAD_ which is an empty range that is both reachable and unreachable from HEAD.

### Other &lt;rev&gt;^ Parent Shorthand Notations

Three other shorthands exist, particularly useful for merge commits, for naming a set that is formed by a commit and its parent commits.

The _r1^@_ notation means all parents of _r1_.

The _r1^!_ notation includes commit _r1_ but excludes all of its parents. By itself, this notation denotes the single commit _r1_.

The _&lt;rev&gt;^-\[&lt;n&gt;\]_ notation includes _&lt;rev&gt;_ but excludes the &lt;n&gt;th parent (i.e. a shorthand for _&lt;rev&gt;^&lt;n&gt;..&lt;rev&gt;_), with _&lt;n&gt;_ = 1 if not given. This is typically useful for merge commits where you can just pass _&lt;commit&gt;^-_ to get all the commits in the branch that was merged in merge commit _&lt;commit&gt;_ (including _&lt;commit&gt;_ itself).

While _&lt;rev&gt;^&lt;n&gt;_ was about specifying a single commit parent, these three notations also consider its parents. For example you can say _HEAD^2^@_, however you cannot say _HEAD^@^2_.

## Revision Range Summary

_&lt;rev&gt;_  
Include commits that are reachable from &lt;rev&gt; (i.e. &lt;rev&gt; and its ancestors).

_^&lt;rev&gt;_  
Exclude commits that are reachable from &lt;rev&gt; (i.e. &lt;rev&gt; and its ancestors).

_&lt;rev1&gt;..&lt;rev2&gt;_  
Include commits that are reachable from &lt;rev2&gt; but exclude those that are reachable from &lt;rev1&gt;. When either &lt;rev1&gt; or &lt;rev2&gt; is omitted, it defaults to `HEAD`.

_&lt;rev1&gt;...&lt;rev2&gt;_  
Include commits that are reachable from either &lt;rev1&gt; or &lt;rev2&gt; but exclude those that are reachable from both. When either &lt;rev1&gt; or &lt;rev2&gt; is omitted, it defaults to `HEAD`.

_&lt;rev&gt;^@_, e.g. _HEAD^@_  
A suffix _^_ followed by an at sign is the same as listing all parents of _&lt;rev&gt;_ (meaning, include anything reachable from its parents, but not the commit itself).

_&lt;rev&gt;^!_, e.g. _HEAD^!_  
A suffix _^_ followed by an exclamation mark is the same as giving commit _&lt;rev&gt;_ and then all its parents prefixed with _^_ to exclude them (and their ancestors).

_&lt;rev&gt;^-&lt;n&gt;_, e.g. _HEAD^-, HEAD^-2_  
Equivalent to _&lt;rev&gt;^&lt;n&gt;..&lt;rev&gt;_, with _&lt;n&gt;_ = 1 if not given.

Here are a handful of examples using the Loeliger illustration above, with each step in the notation’s expansion and selection carefully spelt out:

       Args   Expanded arguments    Selected commits
       D                            G H D
       D F                          G H I J D F
       ^G D                         H D
       ^D B                         E I J F B
       ^D B C                       E I J F B C
       C                            I J F C
       B..C   = ^B C                C
       B...C  = B ^F C              G H D E B C
       B^-    = B^..B
              = ^B^1 B              E I J F B
       C^@    = C^1
              = F                   I J F
       B^@    = B^1 B^2 B^3
              = D E F               D G H E F I J
       C^!    = C ^C^@
              = C ^C^1
              = C ^F                C
       B^!    = B ^B^@
              = B ^B^1 ^B^2 ^B^3
              = B ^D ^E ^F          B
       F^! D  = F ^I ^J D           G H D F

## SEE ALSO

[git-rev-parse(1)](git-rev-parse.html)

## GIT
