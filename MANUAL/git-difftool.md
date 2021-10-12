# git-difftool(1) Manual Page

## NAME

git-difftool - Show changes using common diff tools

## SYNOPSIS

    git difftool [<options>] [<commit> [<commit>]] [--] [<path>…​]

## DESCRIPTION

_git difftool_ is a Git command that allows you to compare and edit files between revisions using common diff tools. _git difftool_ is a frontend to _git diff_ and accepts the same options and arguments. See [git-diff(1)](git-diff.html).

## OPTIONS

-d  
--dir-diff  
Copy the modified files to a temporary location and perform a directory diff on them. This mode never prompts before launching the diff tool.

-y  
--no-prompt  
Do not prompt before launching a diff tool.

--prompt  
Prompt before each invocation of the diff tool. This is the default behaviour; the option is provided to override any configuration settings.

--rotate-to=&lt;file&gt;  
Start showing the diff for the given path, the paths before it will move to end and output.

--skip-to=&lt;file&gt;  
Start showing the diff for the given path, skipping all the paths before it.

-t &lt;tool&gt;  
--tool=&lt;tool&gt;  
Use the diff tool specified by &lt;tool&gt;. Valid values include emerge, kompare, meld, and vimdiff. Run `git difftool --tool-help` for the list of valid &lt;tool&gt; settings.

If a diff tool is not specified, _git difftool_ will use the configuration variable `diff.tool`. If the configuration variable `diff.tool` is not set, _git difftool_ will pick a suitable default.

You can explicitly provide a full path to the tool by setting the configuration variable `difftool.<tool>.path`. For example, you can configure the absolute path to kdiff3 by setting `difftool.kdiff3.path`. Otherwise, _git difftool_ assumes the tool is available in PATH.

Instead of running one of the known diff tools, _git difftool_ can be customized to run an alternative program by specifying the command line to invoke in a configuration variable `difftool.<tool>.cmd`.

When _git difftool_ is invoked with this tool (either through the `-t` or `--tool` option or the `diff.tool` configuration variable) the configured command line will be invoked with the following variables available: `$LOCAL` is set to the name of the temporary file containing the contents of the diff pre-image and `$REMOTE` is set to the name of the temporary file containing the contents of the diff post-image. `$MERGED` is the name of the file which is being compared. `$BASE` is provided for compatibility with custom merge tool commands and has the same value as `$MERGED`.

--tool-help  
Print a list of diff tools that may be used with `--tool`.

--\[no-\]symlinks  
_git difftool_'s default behavior is create symlinks to the working tree when run in `--dir-diff` mode and the right-hand side of the comparison yields the same content as the file in the working tree.

Specifying `--no-symlinks` instructs _git difftool_ to create copies instead. `--no-symlinks` is the default on Windows.

-x &lt;command&gt;  
--extcmd=&lt;command&gt;  
Specify a custom command for viewing diffs. _git-difftool_ ignores the configured defaults and runs `$command $LOCAL $REMOTE` when this option is specified. Additionally, `$BASE` is set in the environment.

-g  
--\[no-\]gui  
When _git-difftool_ is invoked with the `-g` or `--gui` option the default diff tool will be read from the configured `diff.guitool` variable instead of `diff.tool`. The `--no-gui` option can be used to override this setting. If `diff.guitool` is not set, we will fallback in the order of `merge.guitool`, `diff.tool`, `merge.tool` until a tool is found.

--\[no-\]trust-exit-code  
_git-difftool_ invokes a diff tool individually on each file. Errors reported by the diff tool are ignored by default. Use `--trust-exit-code` to make _git-difftool_ exit when an invoked diff tool returns a non-zero exit code.

_git-difftool_ will forward the exit code of the invoked tool when `--trust-exit-code` is used.

See [git-diff(1)](git-diff.html) for the full list of supported options.

## CONFIG VARIABLES

_git difftool_ falls back to _git mergetool_ config variables when the difftool equivalents have not been defined.

diff.tool  
The default diff tool to use.

diff.guitool  
The default diff tool to use when `--gui` is specified.

difftool.&lt;tool&gt;.path  
Override the path for the given tool. This is useful in case your tool is not in the PATH.

difftool.&lt;tool&gt;.cmd  
Specify the command to invoke the specified diff tool.

See the `--tool=<tool>` option above for more details.

difftool.prompt  
Prompt before each invocation of the diff tool.

difftool.trustExitCode  
Exit difftool if the invoked diff tool returns a non-zero exit status.

See the `--trust-exit-code` option above for more details.

## SEE ALSO

[git-diff(1)](git-diff.html)  
Show changes between commits, commit and working tree, etc

[git-mergetool(1)](git-mergetool.html)  
Run merge conflict resolution tools to resolve merge conflicts

[git-config(1)](git-config.html)  
Get and set repository or global options

## GIT

Part of the [git(1)](git.html) suite

Last updated 2021-03-27 09:47:30 UTC
