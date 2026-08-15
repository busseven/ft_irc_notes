# ft_irc_notes

**IMPORTANT: Click on a link while holding CTRL so that it opens in a new tab.**<br><br>
## Branching model
Decision: [trunk-based development](https://trunkbaseddevelopment.com/) with short-lived feature [branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository), and no
develop branch.

• main is always compilable and always runnable. If main is broken, that is a stop-the-world
event.<br><br>
• Every piece of work happens on a branch named **<owner\>/<area\>-<short-description\>** , for
example emir/net-poll-loop or kuzey/cmd-mode-k<br><br>
• A branch lives at most **one day**. If your branch is older than 24 hours, it is too big; [split it](https://github.com/djpohly/git-split-branch/blob/master/README.md).<br><br>
• You merge into main through a [pull request](https://docs.github.com/en/pull-requests/reference), always, even for a two-line fix.<br><br>

## Branch protection rules
On GitHub: Settings, Branches, Add rule for main.<br>

• Require a [pull request](https://docs.github.com/en/pull-requests/reference) before merging.<br><br>
• Require approvals: 1. Yes, this means you [review](https://docs.github.com/en/pull-requests/how-tos/review-pull-requests) each other. This is the mechanism that
guarantees both of you understand the whole codebase by the defence, which is a
subject requirement in disguise.<br><br>
• Require status checks to pass before merging: select the CI job you create in 2.4.7.<br><br>
• Require branches to be up to date before merging: on. This forces the person merging
second to rebase, which surfaces conflicts in their own branch rather than in main.<br><br>
• Do not enable “require linear history” plus “squash only” plus signed commits plus
everything else GitHub offers. Every additional rule is a chance to be blocked at 2 a.m.
by your own configuration.<br><br>
*Trap.* If you are a two-person team and you enable “require approvals” with “dismiss stale
approvals”, you can lock yourselves out when one person is asleep and the other has a one-
line fix for a broken main . *Keep an escape hatch: repository administrators can bypass.
Agree verbally that the bypass is used only for “ main does not compile” and that the
bypassing person posts in Slack immediately.*<br><br>

## Allowed functions

Everything in C++ 98.
|     |     |     |     |     |
| --- | --- | --- | --- | --- |
| [socket](https://man7.org/linux/man-pages/man2/socket.2.html)|[close](https://man7.org/linux/man-pages/man2/close.2.html)|[setsockopt](https://man7.org/linux/man-pages/man3/setsockopt.3p.html)|[getsockname](https://man7.org/linux/man-pages/man2/getsockname.2.html)| [getprotobyname](https://man7.org/linux/man-pages/man3/getprotobyname.3p.html)|
|[gethostbyname](https://man7.org/linux/man-pages/man3/gethostbyname.3.html)|[getaddrinfo](https://man7.org/linux/man-pages/man3/getaddrinfo.3.html)|[freeaddrinfo](https://man7.org/linux/man-pages/man3/freeaddrinfo.3p.html)|[bind](https://man7.org/linux/man-pages/man2/bind.2.html)| [connect](https://man7.org/linux/man-pages/man2/connect.2.html)|
|[listen](https://man7.org/linux/man-pages/man2/listen.2.html)|[accept](https://man7.org/linux/man-pages/man2/accept.2.html)|[htons](https://linux.die.net/man/3/htons)|[htonl](https://linux.die.net/man/3/htonl)|[ntohs](https://linux.die.net/man/3/ntohs)|
|[ntohl](https://linux.die.net/man/3/ntohl)|[inet_addr](https://linux.die.net/man/3/inet_addr)|[inet_ntoa](https://linux.die.net/man/3/inet_ntoa)|[inet_ntop](https://man7.org/linux/man-pages/man3/inet_ntop.3.html)|[send](https://man7.org/linux/man-pages/man2/sendmsg.2.html)|
|[recv](https://man7.org/linux/man-pages/man2/recv.2.html)|[signal](https://man7.org/linux/man-pages/man7/signal.7.html)|[sigaction](https://man7.org/linux/man-pages/man2/sigaction.2.html)|[sigemptyset](https://man7.org/linux/man-pages/man3/sigemptyset.3p.html)|[sigfillset](https://man7.org/linux/man-pages/man3/sigfillset.3p.html)|
|[sigaddset](https://man7.org/linux/man-pages/man3/sigaddset.3p.html)|[sigdelset](https://man7.org/linux/man-pages/man3/sigdelset.3p.html)|[sigismember](https://man7.org/linux/man-pages/man3/sigismember.3p.html)|[lseek](https://man7.org/linux/man-pages/man2/lseek.2.html)|[fstat](https://linux.die.net/man/2/fstat)|
|[fcntl](https://man7.org/linux/man-pages/man2/fcntl.2.html)|[poll](https://man7.org/linux/man-pages/man2/poll.2.html)|[select](https://man7.org/linux/man-pages/man2/select.2.html)*|[kqueue](https://man.openbsd.org/kqueue.2)*|[epoll](https://man7.org/linux/man-pages/man7/epoll.7.html)*|

*Even though poll() is mentioned in the subject and the evaluation scale, you may use any equivalent such as select(), kqueue(), or epoll().
