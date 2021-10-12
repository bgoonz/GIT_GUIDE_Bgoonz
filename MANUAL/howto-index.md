Git Howto Index
===============

Here is a collection of mailing list postings made by various people describing how they use Git in their workflow.

-   [keep-canonical-history-correct](howto/keep-canonical-history-correct.html) by Junio C Hamano &lt;<gitster@pobox.com>&gt;

This how-to explains a method for keeping a project’s history correct when using git pull.

-   [maintain-git](howto/maintain-git.html) by Junio C Hamano &lt;<gitster@pobox.com>&gt;

Imagine that Git development is racing along as usual, when our friendly neighborhood maintainer is struck down by a wayward bus. Out of the hordes of suckers (loyal developers), you have been tricked (chosen) to step up as the new maintainer. This howto will show you "how to" do it.

-   [new-command](howto/new-command.html) by Eric S. Raymond &lt;<esr@thyrsus.com>&gt;

This is how-to documentation for people who want to add extension commands to Git. It should be read alongside api-builtin.txt.

-   [rebase-from-internal-branch](howto/rebase-from-internal-branch.html) by Junio C Hamano &lt;<gitster@pobox.com>&gt;

In this article, JC talks about how he rebases the public "seen" branch using the core Git tools when he updates the "master" branch, and how "rebase" works. Also discussed is how this applies to individual developers who sends patches upstream.

-   [rebuild-from-update-hook](howto/rebuild-from-update-hook.html) by Junio C Hamano &lt;<gitster@pobox.com>&gt;

In this how-to article, JC talks about how he uses the post-update hook to automate Git documentation page shown at <a href="https://www.kernel.org/pub/software/scm/git/docs/" class="bare">https://www.kernel.org/pub/software/scm/git/docs/</a>.

-   [recover-corrupted-blob-object](howto/recover-corrupted-blob-object.html) by Linus Torvalds &lt;<torvalds@linux-foundation.org>&gt;

Some tricks to reconstruct blob objects in order to fix a corrupted repository.

-   [recover-corrupted-object-harder](howto/recover-corrupted-object-harder.html) by Jeff King &lt;<peff@peff.net>&gt;

Recovering a corrupted object when no good copy is available.

-   [revert-a-faulty-merge](howto/revert-a-faulty-merge.html) by Linus Torvalds &lt;<torvalds@linux-foundation.org>&gt;, Junio C Hamano &lt;<gitster@pobox.com>&gt;

Sometimes a branch that was already merged to the mainline is later found to be faulty. Linus and Junio give guidance on recovering from such a premature merge and continuing development after the offending branch is fixed.

-   [revert-branch-rebase](howto/revert-branch-rebase.html) by Junio C Hamano &lt;<gitster@pobox.com>&gt;

In this article, JC gives a small real-life example of using *git revert* command, and using a temporary branch and tag for safety and easier sanity checking.

-   [separating-topic-branches](howto/separating-topic-branches.html) by Junio C Hamano &lt;<gitster@pobox.com>&gt;

In this article, JC describes how to separate topic branches.

-   [setup-git-server-over-http](howto/setup-git-server-over-http.html) by Rutger Nijlunsing &lt;<rutger@nospam.com>&gt;

-   [update-hook-example](howto/update-hook-example.html) by Junio C Hamano &lt;<gitster@pobox.com>&gt; and Carl Baldwin &lt;<cnb@fc.hp.com>&gt;

An example hooks/update script is presented to implement repository maintenance policies, such as who can push into which branch and who can make a tag.

-   [use-git-daemon](howto/use-git-daemon.html)

-   [using-merge-subtree](howto/using-merge-subtree.html) by Sean &lt;<seanlkml@sympatico.ca>&gt;

In this article, Sean demonstrates how one can use the subtree merge strategy.

-   [using-signed-tag-in-pull-request](howto/using-signed-tag-in-pull-request.html) by Junio C Hamano &lt;<gitster@pobox.com>&gt;

Beginning v1.7.9, a contributor can push a signed tag to her publishing repository and ask her integrator to pull it. This assures the integrator that the pulled history is authentic and allows others to later validate it.
