# git-upload-pack(1) Manual Page

## NAME

git-upload-pack - Send objects packed back to git-fetch-pack

## SYNOPSIS

    git-upload-pack [--[no-]strict] [--timeout=<n>] [--stateless-rpc]
                      [--advertise-refs] <directory>

## DESCRIPTION

Invoked by _git fetch-pack_, learns what objects the other side is missing, and sends them after packing.

This command is usually not invoked directly by the end user. The UI for the protocol is on the _git fetch-pack_ side, and the program pair is meant to be used to pull updates from a remote repository. For push operations, see _git send-pack_.

## OPTIONS

--\[no-\]strict  
Do not try &lt;directory&gt;/.git/ if &lt;directory&gt; is no Git directory.

--timeout=&lt;n&gt;  
Interrupt transfer after &lt;n&gt; seconds of inactivity.

--stateless-rpc  
Perform only a single read-write cycle with stdin and stdout. This fits with the HTTP POST request processing model where a program may read the request, write a response, and must exit.

--advertise-refs  
Only the initial ref advertisement is output, and the program exits immediately. This fits with the HTTP GET request model, where no request content is received but a response must be produced.

&lt;directory&gt;  
The repository to sync from.

## SEE ALSO

[gitnamespaces(7)](gitnamespaces.html)

## GIT
