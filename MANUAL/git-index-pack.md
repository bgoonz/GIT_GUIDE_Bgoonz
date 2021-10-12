git-index-pack(1) Manual Page
=============================

NAME
----

git-index-pack - Build pack index file for an existing packed archive

SYNOPSIS
--------

    git index-pack [-v] [-o <index-file>] [--[no-]rev-index] <pack-file>
    git index-pack --stdin [--fix-thin] [--keep] [-v] [-o <index-file>]
                      [--[no-]rev-index] [<pack-file>]

DESCRIPTION
-----------

Reads a packed archive (.pack) from the specified file, and builds a pack index file (.idx) for it. Optionally writes a reverse-index (.rev) for the specified pack. The packed archive together with the pack index can then be placed in the objects/pack/ directory of a Git repository.

OPTIONS
-------

-v  
Be verbose about what is going on, including progress status.

-o &lt;index-file&gt;  
Write the generated pack index into the specified file. Without this option the name of pack index file is constructed from the name of packed archive file by replacing .pack with .idx (and the program fails if the name of packed archive does not end with .pack).

--\[no-\]rev-index  
When this flag is provided, generate a reverse index (a `.rev` file) corresponding to the given pack. If `--verify` is given, ensure that the existing reverse index is correct. Takes precedence over `pack.writeReverseIndex`.

--stdin  
When this flag is provided, the pack is read from stdin instead and a copy is then written to &lt;pack-file&gt;. If &lt;pack-file&gt; is not specified, the pack is written to objects/pack/ directory of the current Git repository with a default name determined from the pack content. If &lt;pack-file&gt; is not specified consider using --keep to prevent a race condition between this process and *git repack*.

--fix-thin  
Fix a "thin" pack produced by `git pack-objects --thin` (see [git-pack-objects(1)](git-pack-objects.html) for details) by adding the excluded objects the deltified objects are based on to the pack. This option only makes sense in conjunction with --stdin.

--keep  
Before moving the index into its final destination create an empty .keep file for the associated pack file. This option is usually necessary with --stdin to prevent a simultaneous *git repack* process from deleting the newly constructed pack and index before refs can be updated to use objects contained in the pack.

--keep=&lt;msg&gt;  
Like --keep create a .keep file before moving the index into its final destination, but rather than creating an empty file place *&lt;msg&gt;* followed by an LF into the .keep file. The *&lt;msg&gt;* message can later be searched for within all .keep files to locate any which have outlived their usefulness.

 --index-version=&lt;version&gt;\[,&lt;offset&gt;\]   
This is intended to be used by the test suite only. It allows to force the version for the generated pack index, and to force 64-bit index entries on objects located above the given offset.

--strict  
Die, if the pack contains broken objects or links.

--check-self-contained-and-connected  
Die if the pack contains broken links. For internal use only.

--fsck-objects  
For internal use only.

Die if the pack contains broken objects. If the pack contains a tree pointing to a .gitmodules blob that does not exist, prints the hash of that blob (for the caller to check) after the hash that goes into the name of the pack/idx file (see "Notes").

--threads=&lt;n&gt;  
Specifies the number of threads to spawn when resolving deltas. This requires that index-pack be compiled with pthreads otherwise this option is ignored with a warning. This is meant to reduce packing time on multiprocessor machines. The required amount of memory for the delta search window is however multiplied by the number of threads. Specifying 0 will cause Git to auto-detect the number of CPU’s and use maximum 3 threads.

--max-input-size=&lt;size&gt;  
Die, if the pack is larger than &lt;size&gt;.

--object-format=&lt;hash-algorithm&gt;  
Specify the given object format (hash algorithm) for the pack. The valid values are *sha1* and (if enabled) *sha256*. The default is the algorithm for the current repository (set by `extensions.objectFormat`), or *sha1* if no value is set or outside a repository.

This option cannot be used with --stdin.

THIS OPTION IS EXPERIMENTAL! SHA-256 support is experimental and still in an early stage. A SHA-256 repository will in general not be able to share work with "regular" SHA-1 repositories. It should be assumed that, e.g., Git internal file formats in relation to SHA-256 repositories may change in backwards-incompatible ways. Only use `--object-format=sha256` for testing purposes.

NOTES
-----

Once the index has been created, the hash that goes into the name of the pack/idx file is printed to stdout. If --stdin was also used then this is prefixed by either "pack\\t", or "keep\\t" if a new .keep file was successfully created. This is useful to remove a .keep file used as a lock to prevent the race with *git repack* mentioned above.

GIT
---

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC