# git-help(1) Manual Page

## NAME

git-help - Display help information about Git

## SYNOPSIS

    git help [-a|--all [--[no-]verbose]] [-g|--guides]
               [-i|--info|-m|--man|-w|--web] [COMMAND|GUIDE]

## DESCRIPTION

With no options and no COMMAND or GUIDE given, the synopsis of the _git_ command and a list of the most commonly used Git commands are printed on the standard output.

If the option `--all` or `-a` is given, all available commands are printed on the standard output.

If the option `--guides` or `-g` is given, a list of the Git concept guides is also printed on the standard output.

If a command, or a guide, is given, a manual page for that command or guide is brought up. The _man_ program is used by default for this purpose, but this can be overridden by other options or configuration variables.

If an alias is given, git shows the definition of the alias on standard output. To get the manual page for the aliased command, use `git COMMAND --help`.

Note that `git --help ...` is identical to `git help ...` because the former is internally converted into the latter.

To display the [git(1)](git.html) man page, use `git help git`.

This page can be displayed with _git help help_ or `git help --help`

## OPTIONS

-a  
--all  
Prints all the available commands on the standard output. This option overrides any given command or guide name.

--verbose  
When used with `--all` print description for all recognized commands. This is the default.

-c  
--config  
List all available configuration variables. This is a short summary of the list in [git-config(1)](git-config.html).

-g  
--guides  
Prints a list of the Git concept guides on the standard output. This option overrides any given command or guide name.

-i  
--info  
Display manual page for the command in the _info_ format. The _info_ program will be used for that purpose.

-m  
--man  
Display manual page for the command in the _man_ format. This option may be used to override a value set in the `help.format` configuration variable.

By default the _man_ program will be used to display the manual page, but the `man.viewer` configuration variable may be used to choose other display programs (see below).

-w  
--web  
Display manual page for the command in the _web_ (HTML) format. A web browser will be used for that purpose.

The web browser can be specified using the configuration variable `help.browser`, or `web.browser` if the former is not set. If none of these config variables is set, the _git web--browse_ helper script (called by _git help_) will pick a suitable default. See [git-web--browse(1)](git-web--browse.html) for more information about this.

## CONFIGURATION VARIABLES

### help.format

If no command-line option is passed, the `help.format` configuration variable will be checked. The following values are supported for this variable; they make _git help_ behave as their corresponding command- line option:

- "man" corresponds to _-m|--man_,

- "info" corresponds to _-i|--info_,

- "web" or "html" correspond to _-w|--web_.

### help.browser, web.browser and browser.&lt;tool&gt;.path

The `help.browser`, `web.browser` and `browser.<tool>.path` will also be checked if the _web_ format is chosen (either by command-line option or configuration variable). See _-w|--web_ in the OPTIONS section above and [git-web--browse(1)](git-web--browse.html).

### man.viewer

The `man.viewer` configuration variable will be checked if the _man_ format is chosen. The following values are currently supported:

- "man": use the _man_ program as usual,

- "woman": use _emacsclient_ to launch the "woman" mode in emacs (this only works starting with emacsclient versions 22),

- "konqueror": use _kfmclient_ to open the man page in a new konqueror tab (see _Note about konqueror_ below).

Values for other tools can be used if there is a corresponding `man.<tool>.cmd` configuration entry (see below).

Multiple values may be given to the `man.viewer` configuration variable. Their corresponding programs will be tried in the order listed in the configuration file.

For example, this configuration:

            [man]
                    viewer = konqueror
                    viewer = woman

will try to use konqueror first. But this may fail (for example, if DISPLAY is not set) and in that case emacs' woman mode will be tried.

If everything fails, or if no viewer is configured, the viewer specified in the `GIT_MAN_VIEWER` environment variable will be tried. If that fails too, the _man_ program will be tried anyway.

### man.&lt;tool&gt;.path

You can explicitly provide a full path to your preferred man viewer by setting the configuration variable `man.<tool>.path`. For example, you can configure the absolute path to konqueror by setting _man.konqueror.path_. Otherwise, _git help_ assumes the tool is available in PATH.

### man.&lt;tool&gt;.cmd

When the man viewer, specified by the `man.viewer` configuration variables, is not among the supported ones, then the corresponding `man.<tool>.cmd` configuration variable will be looked up. If this variable exists then the specified tool will be treated as a custom command and a shell eval will be used to run the command with the man page passed as arguments.

### Note about konqueror

When _konqueror_ is specified in the `man.viewer` configuration variable, we launch _kfmclient_ to try to open the man page on an already opened konqueror in a new tab if possible.

For consistency, we also try such a trick if _man.konqueror.path_ is set to something like `A_PATH_TO/konqueror`. That means we will try to launch `A_PATH_TO/kfmclient` instead.

If you really want to use _konqueror_, then you can use something like the following:

            [man]
                    viewer = konq

            [man "konq"]
                    cmd = A_PATH_TO/konqueror

### Note about git config --global

Note that all these configuration variables should probably be set using the `--global` flag, for example like this:

    $ git config --global help.format web
    $ git config --global web.browser firefox

as they are probably more user specific than repository specific. See [git-config(1)](git-config.html) for more information about this.

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
