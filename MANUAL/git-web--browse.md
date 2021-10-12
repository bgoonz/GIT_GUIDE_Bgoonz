git-web--browse(1) Manual Page
==============================

NAME
----

git-web--browse - Git helper script to launch a web browser

SYNOPSIS
--------

    git web--browse [<options>] <url|file>…​

DESCRIPTION
-----------

This script tries, as much as possible, to display the URLs and FILEs that are passed as arguments, as HTML pages in new tabs on an already opened web browser.

The following browsers (or commands) are currently supported:

-   firefox (this is the default under X Window when not using KDE)

-   iceweasel

-   seamonkey

-   iceape

-   chromium (also supported as chromium-browser)

-   google-chrome (also supported as chrome)

-   konqueror (this is the default under KDE, see *Note about konqueror* below)

-   opera

-   w3m (this is the default outside graphical environments)

-   elinks

-   links

-   lynx

-   dillo

-   open (this is the default under Mac OS X GUI)

-   start (this is the default under MinGW)

-   cygstart (this is the default under Cygwin)

-   xdg-open

Custom commands may also be specified.

OPTIONS
-------

-b &lt;browser&gt;  
--browser=&lt;browser&gt;  
Use the specified browser. It must be in the list of supported browsers.

-t &lt;browser&gt;  
--tool=&lt;browser&gt;  
Same as above.

-c &lt;conf.var&gt;  
--config=&lt;conf.var&gt;  
CONF.VAR is looked up in the Git config files. If it’s set, then its value specifies the browser that should be used.

CONFIGURATION VARIABLES
-----------------------

### CONF.VAR (from -c option) and web.browser

The web browser can be specified using a configuration variable passed with the -c (or --config) command-line option, or the `web.browser` configuration variable if the former is not used.

### browser.&lt;tool&gt;.path

You can explicitly provide a full path to your preferred browser by setting the configuration variable `browser.<tool>.path`. For example, you can configure the absolute path to firefox by setting *browser.firefox.path*. Otherwise, *git web--browse* assumes the tool is available in PATH.

### browser.&lt;tool&gt;.cmd

When the browser, specified by options or configuration variables, is not among the supported ones, then the corresponding `browser.<tool>.cmd` configuration variable will be looked up. If this variable exists then *git web--browse* will treat the specified tool as a custom command and will use a shell eval to run the command with the URLs passed as arguments.

NOTE ABOUT KONQUEROR
--------------------

When *konqueror* is specified by a command-line option or a configuration variable, we launch *kfmclient* to try to open the HTML man page on an already opened konqueror in a new tab if possible.

For consistency, we also try such a trick if *browser.konqueror.path* is set to something like `A_PATH_TO/konqueror`. That means we will try to launch `A_PATH_TO/kfmclient` instead.

If you really want to use *konqueror*, then you can use something like the following:

            [web]
                    browser = konq

            [browser "konq"]
                    cmd = A_PATH_TO/konqueror

### Note about git-config --global

Note that these configuration variables should probably be set using the `--global` flag, for example like this:

    $ git config --global web.browser firefox

as they are probably more user specific than repository specific. See [git-config(1)](git-config.html) for more information about this.

GIT
---
