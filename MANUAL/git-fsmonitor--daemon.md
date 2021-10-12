git-fsmonitor—​daemon(1) Manual Page
====================================

NAME
----

git-fsmonitor--daemon - (EXPERIMENTAL) Builtin file system monitor daemon

SYNOPSIS
--------

    git fsmonitor—​daemon --start
    git fsmonitor—​daemon --run
    git fsmonitor—​daemon --stop
    git fsmonitor—​daemon --is-running
    git fsmonitor—​daemon --is-supported
    git fsmonitor—​daemon --query <token>
    git fsmonitor—​daemon --query-index
    git fsmonitor—​daemon --flush

DESCRIPTION
-----------

NOTE! This command is still only an experiment, subject to change dramatically (or even to be abandoned).

Monitors files and directories in the working directory for changes using platform-specific file system notification facilities.

It communicates directly with commands like `git status` using the [simple IPC](technical/api-simple-ipc.html) interface instead of the slower [githooks(5)](githooks.html) interface.

OPTIONS
-------

--start  
Starts the fsmonitor daemon in the background.

--run  
Runs the fsmonitor daemon in the foreground.

--stop  
Stops the fsmonitor daemon running for the current working directory, if present.

--is-running  
Exits with zero status if the fsmonitor daemon is watching the current working directory.

--is-supported  
Exits with zero status if the fsmonitor daemon feature is supported on this platform.

--query &lt;token&gt;  
Connects to the fsmonitor daemon (starting it if necessary) and requests the list of changed files and directories since the given token. This is intended for testing purposes.

--query-index  
Read the current `<token>` from the File System Monitor index extension (if present) and use it to query the fsmonitor daemon. This is intended for testing purposes.

--flush  
Force the fsmonitor daemon to flush its in-memory cache and re-sync with the file system. This is intended for testing purposes.

REMARKS
-------

The fsmonitor daemon is a long running process that will watch a single working directory. Commands, such as `git status`, should automatically start it (if necessary) when `core.useBuiltinFSMonitor` is set to `true` (see [git-config(1)](git-config.html)).

Configure the built-in FSMonitor via `core.useBuiltinFSMonitor` in each working directory separately, or globally via `git config --global core.useBuiltinFSMonitor true`.

Tokens are opaque strings. They are used by the fsmonitor daemon to mark a point in time and the associated internal state. Callers should make no assumptions about the content of the token. In particular, the should not assume that it is a timestamp.

Query commands send a request-token to the daemon and it responds with a summary of the changes that have occurred since that token was created. The daemon also returns a response-token that the client can use in a future query.

For more information see the "File System Monitor" section in [git-update-index(1)](git-update-index.html).

CAVEATS
-------

The fsmonitor daemon does not currently know about submodules and does not know to filter out file system events that happen within a submodule. If fsmonitor daemon is watching a super repo and a file is modified within the working directory of a submodule, it will report the change (as happening against the super repo). However, the client should properly ignore these extra events, so performance may be affected but it should not cause an incorrect result.

GIT
---

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
