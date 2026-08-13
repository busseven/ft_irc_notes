# ft_irc_notes

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
