# git-credential-cache—​daemon(1) Manual Page

## NAME

git-credential-cache--daemon - Temporarily store user credentials in memory

## SYNOPSIS

    git credential-cache—​daemon [--debug] <socket>

## DESCRIPTION

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><div class="title">Note</div></td><td>You probably don’t want to invoke this command yourself; it is started automatically when you use <a href="git-credential-cache.html">git-credential-cache(1)</a>.</td></tr></tbody></table>

This command listens on the Unix domain socket specified by `<socket>` for `git-credential-cache` clients. Clients may store and retrieve credentials. Each credential is held for a timeout specified by the client; once no credentials are held, the daemon exits.

If the `--debug` option is specified, the daemon does not close its stderr stream, and may output extra diagnostics to it even after it has begun listening for clients.

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
