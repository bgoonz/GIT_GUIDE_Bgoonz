# gitremote-helpers(7) Manual Page

## NAME

gitremote-helpers - Helper programs to interact with remote repositories

## SYNOPSIS

    git remote-<transport> <repository> [<URL>]

## DESCRIPTION

Remote helper programs are normally not used directly by end users, but they are invoked by Git when it needs to interact with remote repositories Git does not support natively. A given helper will implement a subset of the capabilities documented here. When Git needs to interact with a repository using a remote helper, it spawns the helper as an independent process, sends commands to the helper’s standard input, and expects results from the helper’s standard output. Because a remote helper runs as an independent process from Git, there is no need to re-link Git to add a new helper, nor any need to link the helper with the implementation of Git.

Every helper must support the "capabilities" command, which Git uses to determine what other commands the helper will accept. Those other commands can be used to discover and update remote refs, transport objects between the object database and the remote repository, and update the local object store.

Git comes with a "curl" family of remote helpers, that handle various transport protocols, such as _git-remote-http_, _git-remote-https_, _git-remote-ftp_ and _git-remote-ftps_. They implement the capabilities _fetch_, _option_, and _push_.

## INVOCATION

Remote helper programs are invoked with one or (optionally) two arguments. The first argument specifies a remote repository as in Git; it is either the name of a configured remote or a URL. The second argument specifies a URL; it is usually of the form _&lt;transport&gt;://&lt;address&gt;_, but any arbitrary string is possible. The `GIT_DIR` environment variable is set up for the remote helper and can be used to determine where to store additional data or from which directory to invoke auxiliary Git commands.

When Git encounters a URL of the form _&lt;transport&gt;://&lt;address&gt;_, where _&lt;transport&gt;_ is a protocol that it cannot handle natively, it automatically invokes _git remote-&lt;transport&gt;_ with the full URL as the second argument. If such a URL is encountered directly on the command line, the first argument is the same as the second, and if it is encountered in a configured remote, the first argument is the name of that remote.

A URL of the form _&lt;transport&gt;::&lt;address&gt;_ explicitly instructs Git to invoke _git remote-&lt;transport&gt;_ with _&lt;address&gt;_ as the second argument. If such a URL is encountered directly on the command line, the first argument is _&lt;address&gt;_, and if it is encountered in a configured remote, the first argument is the name of that remote.

Additionally, when a configured remote has `remote.<name>.vcs` set to _&lt;transport&gt;_, Git explicitly invokes _git remote-&lt;transport&gt;_ with _&lt;name&gt;_ as the first argument. If set, the second argument is `remote.<name>.url`; otherwise, the second argument is omitted.

## INPUT FORMAT

Git sends the remote helper a list of commands on standard input, one per line. The first command is always the _capabilities_ command, in response to which the remote helper must print a list of the capabilities it supports (see below) followed by a blank line. The response to the capabilities command determines what commands Git uses in the remainder of the command stream.

The command stream is terminated by a blank line. In some cases (indicated in the documentation of the relevant commands), this blank line is followed by a payload in some other protocol (e.g., the pack protocol), while in others it indicates the end of input.

### Capabilities

Each remote helper is expected to support only a subset of commands. The operations a helper supports are declared to Git in the response to the `capabilities` command (see COMMANDS, below).

In the following, we list all defined capabilities and for each we list which commands a helper with that capability must provide.

#### Capabilities for Pushing

_connect_  
Can attempt to connect to _git receive-pack_ (for pushing), _git upload-pack_, etc for communication using git’s native packfile protocol. This requires a bidirectional, full-duplex connection.

Supported commands: _connect_.

_stateless-connect_  
Experimental; for internal use only. Can attempt to connect to a remote server for communication using git’s wire-protocol version 2. See the documentation for the stateless-connect command for more information.

Supported commands: _stateless-connect_.

_push_  
Can discover remote refs and push local commits and the history leading up to them to new or existing remote refs.

Supported commands: _list for-push_, _push_.

_export_  
Can discover remote refs and push specified objects from a fast-import stream to remote refs.

Supported commands: _list for-push_, _export_.

If a helper advertises _connect_, Git will use it if possible and fall back to another capability if the helper requests so when connecting (see the _connect_ command under COMMANDS). When choosing between _push_ and _export_, Git prefers _push_. Other frontends may have some other order of preference.

_no-private-update_  
When using the _refspec_ capability, git normally updates the private ref on successful push. This update is disabled when the remote-helper declares the capability _no-private-update_.

#### Capabilities for Fetching

_connect_  
Can try to connect to _git upload-pack_ (for fetching), _git receive-pack_, etc for communication using the Git’s native packfile protocol. This requires a bidirectional, full-duplex connection.

Supported commands: _connect_.

_stateless-connect_  
Experimental; for internal use only. Can attempt to connect to a remote server for communication using git’s wire-protocol version 2. See the documentation for the stateless-connect command for more information.

Supported commands: _stateless-connect_.

_fetch_  
Can discover remote refs and transfer objects reachable from them to the local object store.

Supported commands: _list_, _fetch_.

_import_  
Can discover remote refs and output objects reachable from them as a stream in fast-import format.

Supported commands: _list_, _import_.

_check-connectivity_  
Can guarantee that when a clone is requested, the received pack is self contained and is connected.

If a helper advertises _connect_, Git will use it if possible and fall back to another capability if the helper requests so when connecting (see the _connect_ command under COMMANDS). When choosing between _fetch_ and _import_, Git prefers _fetch_. Other frontends may have some other order of preference.

#### Miscellaneous capabilities

_option_  
For specifying settings like `verbosity` (how much output to write to stderr) and `depth` (how much history is wanted in the case of a shallow clone) that affect how other commands are carried out.

_refspec_ &lt;refspec&gt;  
For remote helpers that implement _import_ or _export_, this capability allows the refs to be constrained to a private namespace, instead of writing to refs/heads or refs/remotes directly. It is recommended that all importers providing the _import_ capability use this. It’s mandatory for _export_.

A helper advertising the capability `refspec refs/heads/*:refs/svn/origin/branches/*` is saying that, when it is asked to `import refs/heads/topic`, the stream it outputs will update the `refs/svn/origin/branches/topic` ref.

This capability can be advertised multiple times. The first applicable refspec takes precedence. The left-hand of refspecs advertised with this capability must cover all refs reported by the list command. If no _refspec_ capability is advertised, there is an implied `refspec *:*`.

When writing remote-helpers for decentralized version control systems, it is advised to keep a local copy of the repository to interact with, and to let the private namespace refs point to this local repository, while the refs/remotes namespace is used to track the remote repository.

_bidi-import_  
This modifies the _import_ capability. The fast-import commands _cat-blob_ and _ls_ can be used by remote-helpers to retrieve information about blobs and trees that already exist in fast-import’s memory. This requires a channel from fast-import to the remote-helper. If it is advertised in addition to "import", Git establishes a pipe from fast-import to the remote-helper’s stdin. It follows that Git and fast-import are both connected to the remote-helper’s stdin. Because Git can send multiple commands to the remote-helper it is required that helpers that use _bidi-import_ buffer all _import_ commands of a batch before sending data to fast-import. This is to prevent mixing commands and fast-import responses on the helper’s stdin.

_export-marks_ &lt;file&gt;  
This modifies the _export_ capability, instructing Git to dump the internal marks table to &lt;file&gt; when complete. For details, read up on `--export-marks=<file>` in [git-fast-export(1)](git-fast-export.html).

_import-marks_ &lt;file&gt;  
This modifies the _export_ capability, instructing Git to load the marks specified in &lt;file&gt; before processing any input. For details, read up on `--import-marks=<file>` in [git-fast-export(1)](git-fast-export.html).

_signed-tags_  
This modifies the _export_ capability, instructing Git to pass `--signed-tags=verbatim` to [git-fast-export(1)](git-fast-export.html). In the absence of this capability, Git will use `--signed-tags=warn-strip`.

_object-format_  
This indicates that the helper is able to interact with the remote side using an explicit hash algorithm extension.

## COMMANDS

Commands are given by the caller on the helper’s standard input, one per line.

_capabilities_  
Lists the capabilities of the helper, one per line, ending with a blank line. Each capability may be preceded with \*\*\*, which marks them mandatory for Git versions using the remote helper to understand. Any unknown mandatory capability is a fatal error.

Support for this command is mandatory.

_list_  
Lists the refs, one per line, in the format "&lt;value&gt; &lt;name&gt; \[&lt;attr&gt; …​\]". The value may be a hex sha1 hash, "@&lt;dest&gt;" for a symref, ":&lt;keyword&gt; &lt;value&gt;" for a key-value pair, or "?" to indicate that the helper could not get the value of the ref. A space-separated list of attributes follows the name; unrecognized attributes are ignored. The list ends with a blank line.

See REF LIST ATTRIBUTES for a list of currently defined attributes. See REF LIST KEYWORDS for a list of currently defined keywords.

Supported if the helper has the "fetch" or "import" capability.

_list for-push_  
Similar to _list_, except that it is used if and only if the caller wants to the resulting ref list to prepare push commands. A helper supporting both push and fetch can use this to distinguish for which operation the output of _list_ is going to be used, possibly reducing the amount of work that needs to be performed.

Supported if the helper has the "push" or "export" capability.

_option_ &lt;name&gt; &lt;value&gt;  
Sets the transport helper option &lt;name&gt; to &lt;value&gt;. Outputs a single line containing one of _ok_ (option successfully set), _unsupported_ (option not recognized) or _error &lt;msg&gt;_ (option &lt;name&gt; is supported but &lt;value&gt; is not valid for it). Options should be set before other commands, and may influence the behavior of those commands.

See OPTIONS for a list of currently defined options.

Supported if the helper has the "option" capability.

_fetch_ &lt;sha1&gt; &lt;name&gt;  
Fetches the given object, writing the necessary objects to the database. Fetch commands are sent in a batch, one per line, terminated with a blank line. Outputs a single blank line when all fetch commands in the same batch are complete. Only objects which were reported in the output of _list_ with a sha1 may be fetched this way.

Optionally may output a _lock &lt;file&gt;_ line indicating the full path of a file under `$GIT_DIR/objects/pack` which is keeping a pack until refs can be suitably updated. The path must end with `.keep`. This is a mechanism to name a &lt;pack,idx,keep&gt; tuple by giving only the keep component. The kept pack will not be deleted by a concurrent repack, even though its objects may not be referenced until the fetch completes. The `.keep` file will be deleted at the conclusion of the fetch.

If option _check-connectivity_ is requested, the helper must output _connectivity-ok_ if the clone is self-contained and connected.

Supported if the helper has the "fetch" capability.

_push_ +&lt;src&gt;:&lt;dst&gt;  
Pushes the given local &lt;src&gt; commit or branch to the remote branch described by &lt;dst&gt;. A batch sequence of one or more _push_ commands is terminated with a blank line (if there is only one reference to push, a single _push_ command is followed by a blank line). For example, the following would be two batches of _push_, the first asking the remote-helper to push the local ref _master_ to the remote ref _master_ and the local `HEAD` to the remote _branch_, and the second asking to push ref _foo_ to ref _bar_ (forced update requested by the _+_).

    push refs/heads/master:refs/heads/master
    push HEAD:refs/heads/branch
    \n
    push +refs/heads/foo:refs/heads/bar
    \n

Zero or more protocol options may be entered after the last _push_ command, before the batch’s terminating blank line.

When the push is complete, outputs one or more _ok &lt;dst&gt;_ or _error &lt;dst&gt; &lt;why&gt;?_ lines to indicate success or failure of each pushed ref. The status report output is terminated by a blank line. The option field &lt;why&gt; may be quoted in a C style string if it contains an LF.

Supported if the helper has the "push" capability.

_import_ &lt;name&gt;  
Produces a fast-import stream which imports the current value of the named ref. It may additionally import other refs as needed to construct the history efficiently. The script writes to a helper-specific private namespace. The value of the named ref should be written to a location in this namespace derived by applying the refspecs from the "refspec" capability to the name of the ref.

Especially useful for interoperability with a foreign versioning system.

Just like _push_, a batch sequence of one or more _import_ is terminated with a blank line. For each batch of _import_, the remote helper should produce a fast-import stream terminated by a _done_ command.

Note that if the _bidi-import_ capability is used the complete batch sequence has to be buffered before starting to send data to fast-import to prevent mixing of commands and fast-import responses on the helper’s stdin.

Supported if the helper has the "import" capability.

_export_  
Instructs the remote helper that any subsequent input is part of a fast-import stream (generated by _git fast-export_) containing objects which should be pushed to the remote.

Especially useful for interoperability with a foreign versioning system.

The _export-marks_ and _import-marks_ capabilities, if specified, affect this command in so far as they are passed on to _git fast-export_, which then will load/store a table of marks for local objects. This can be used to implement for incremental operations.

Supported if the helper has the "export" capability.

_connect_ &lt;service&gt;  
Connects to given service. Standard input and standard output of helper are connected to specified service (git prefix is included in service name so e.g. fetching uses _git-upload-pack_ as service) on remote side. Valid replies to this command are empty line (connection established), _fallback_ (no smart transport support, fall back to dumb transports) and just exiting with error message printed (can’t connect, don’t bother trying to fall back). After line feed terminating the positive (empty) response, the output of service starts. After the connection ends, the remote helper exits.

Supported if the helper has the "connect" capability.

_stateless-connect_ &lt;service&gt;  
Experimental; for internal use only. Connects to the given remote service for communication using git’s wire-protocol version 2. Valid replies to this command are empty line (connection established), _fallback_ (no smart transport support, fall back to dumb transports) and just exiting with error message printed (can’t connect, don’t bother trying to fall back). After line feed terminating the positive (empty) response, the output of the service starts. Messages (both request and response) must consist of zero or more PKT-LINEs, terminating in a flush packet. Response messages will then have a response end packet after the flush packet to indicate the end of a response. The client must not expect the server to store any state in between request-response pairs. After the connection ends, the remote helper exits.

Supported if the helper has the "stateless-connect" capability.

If a fatal error occurs, the program writes the error message to stderr and exits. The caller should expect that a suitable error message has been printed if the child closes the connection without completing a valid response for the current command.

Additional commands may be supported, as may be determined from capabilities reported by the helper.

## REF LIST ATTRIBUTES

The _list_ command produces a list of refs in which each ref may be followed by a list of attributes. The following ref list attributes are defined.

_unchanged_  
This ref is unchanged since the last import or fetch, although the helper cannot necessarily determine what value that produced.

## REF LIST KEYWORDS

The _list_ command may produce a list of key-value pairs. The following keys are defined.

_object-format_  
The refs are using the given hash algorithm. This keyword is only used if the server and client both support the object-format extension.

## OPTIONS

The following options are defined and (under suitable circumstances) set by Git if the remote helper has the _option_ capability.

_option verbosity_ &lt;n&gt;  
Changes the verbosity of messages displayed by the helper. A value of 0 for &lt;n&gt; means that processes operate quietly, and the helper produces only error output. 1 is the default level of verbosity, and higher values of &lt;n&gt; correspond to the number of -v flags passed on the command line.

_option progress_ {_true_|_false_}  
Enables (or disables) progress messages displayed by the transport helper during a command.

_option depth_ &lt;depth&gt;  
Deepens the history of a shallow repository.

'option deepen-since &lt;timestamp&gt;  
Deepens the history of a shallow repository based on time.

'option deepen-not &lt;ref&gt;  
Deepens the history of a shallow repository excluding ref. Multiple options add up.

_option deepen-relative {'true_|_false_}  
Deepens the history of a shallow repository relative to current boundary. Only valid when used with "option depth".

_option followtags_ {_true_|_false_}  
If enabled the helper should automatically fetch annotated tag objects if the object the tag points at was transferred during the fetch command. If the tag is not fetched by the helper a second fetch command will usually be sent to ask for the tag specifically. Some helpers may be able to use this option to avoid a second network connection.

_option dry-run_ {_true_|_false_}: If true, pretend the operation completed successfully, but don’t actually change any repository data. For most helpers this only applies to the _push_, if supported.

_option servpath &lt;c-style-quoted-path&gt;_  
Sets service path (--upload-pack, --receive-pack etc.) for next connect. Remote helper may support this option, but must not rely on this option being set before connect request occurs.

_option check-connectivity_ {_true_|_false_}  
Request the helper to check connectivity of a clone.

_option force_ {_true_|_false_}  
Request the helper to perform a force update. Defaults to _false_.

_option cloning_ {_true_|_false_}  
Notify the helper this is a clone request (i.e. the current repository is guaranteed empty).

_option update-shallow_ {_true_|_false_}  
Allow to extend .git/shallow if the new refs require it.

_option pushcert_ {_true_|_false_}  
GPG sign pushes.

'option push-option &lt;string&gt;  
Transmit &lt;string&gt; as a push option. As the push option must not contain LF or NUL characters, the string is not encoded.

_option from-promisor_ {_true_|_false_}  
Indicate that these objects are being fetched from a promisor.

_option no-dependents_ {_true_|_false_}  
Indicate that only the objects wanted need to be fetched, not their dependents.

_option atomic_ {_true_|_false_}  
When pushing, request the remote server to update refs in a single atomic transaction. If successful, all refs will be updated, or none will. If the remote side does not support this capability, the push will fail.

_option object-format_ {_true_|algorithm}  
If _true_, indicate that the caller wants hash algorithm information to be passed back from the remote. This mode is used when fetching refs.

If set to an algorithm, indicate that the caller wants to interact with the remote side using that algorithm.

## SEE ALSO

[git-remote(1)](git-remote.html)

[git-remote-ext(1)](git-remote-ext.html)

[git-remote-fd(1)](git-remote-fd.html)

[git-fast-import(1)](git-fast-import.html)

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
