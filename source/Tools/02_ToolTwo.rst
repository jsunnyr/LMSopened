================================
Nginx [Nginx]_ [1]_ [2]_
================================
introduction to Nginx.
------------------------
.. image:: ../images/nginx.png
.. [Nginx] https://nginx.org/
.. [1]	https://nginx.org/
.. [2]	https://en.wikipedia.org/wiki/Nginx

.. note:: Official Announcement.

nginx [engine x]是最初由Igor Sysoev编写的HTTP和反向代理服务器，邮件代理服务器和通用TCP / UDP代理服务器。很长一段时间以来，它一直在许多重负荷的俄罗斯网站上运行，包括 Yandex， Mail.Ru， VK和 Rambler。根据Netcraft，2018年2月，nginx服务或代理了 25.92％最繁忙的站点.

- 基本的HTTP服务器功能
	- 提供静态和 索引 文件， 自动索引 ; 打开文件描述符缓存 ;
	- 通过缓存加速反向代理 ; 负载平衡和容错 ;
	- 通过缓存FastCGI， uwsgi， SCGI和 memcached 服务器加速支持 ; 负载平衡和容错 ;
	- 模块化架构。过滤器包括 gzipping，字节范围，分块响应， XSLT， SSI和图像转换过滤器。如果通过代理或FastCGI / uwsgi / SCGI服务器处理单个页面内的多个SSI包含，可以并行处理;
	- SSL和TLS SNI支持 ;
	- 支持 具有加权和依赖性优先级的HTTP / 2。

- 其他HTTP服务器功能
	- 基于名称和基于IP的 虚拟服务器 ;
	- 保持活跃 和流水线连接支持;
	- 访问日志格式， 缓冲日志写入， 快速日志轮换和 系统日志日志记录 ;
	- 3xx-5xx错误代码 重定向 ;
	- 重写模块： 使用正则表达式更改URI ;
	- 根据 客户端地址执行不同的功能 ;
	- 基于客户端IP地址， 密码（HTTP基本认证）和 子请求结果的访问控制 ;
	- HTTP referer的 验证 ;
	- 该PUT，DELETE，MKCOL，复制和移动方法;
	- FLV 和 MP4 流媒体;
	- 响应速率限制 ;
	- 限制 来自一个地址的同时连接 或 请求的数量 ;
	- 基于IP的地理位置 ;
	- A / B测试 ;
	- 请求镜像 ;
	- 嵌入式Perl ;
	- nginScript。

- 邮件代理服务器功能
	- 用户 使用外部HTTP 认证 服务器重定向到 IMAP 或 POP3服务器;
	- 使用外部HTTP 认证 服务器的用户认证 和连接重定向到内部 SMTP服务器;
	- 认证方法：
		- POP3：USER / PASS，APOP，AUTH LOGIN / PLAIN / CRAM-MD5;
		- IMAP：LOGIN，AUTH LOGIN / PLAIN / CRAM-MD5;
		- SMTP：AUTH LOGIN / PLAIN / CRAM-MD5;
	- SSL支持;
	- STARTTLS和STLS支持。

- TCP / UDP代理服务器功能
	- TCP和UDP的通用代理 ;
	- SSL和TLS SNI支持TCP;
	- 负载平衡和容错 ;
	- 基于客户端地址的访问控制 ;
	- 根据客户端地址执行不同的功能 ;
	- 限制 来自一个地址的同时连接的数量 ;
	- 访问日志格式， 缓冲日志写入， 快速日志轮换和 系统日志日志记录 ;
	- 基于IP的地理位置 ;
	- A / B测试 ;
	- nginScript。

- 体系结构和可扩展性
	- 一个主人和几个工人进程; 工作进程在非特权用户下运行;
	- 灵活的配置 ;
	- 在不中断客户服务的情况下重新配置 和升级可执行文件 ;
	- 支持 kqueue（FreeBSD 4.1+），epoll（Linux 2.6+），/ dev / poll（Solaris 7 11/99 +），事件端口（Solaris 10），select和poll;
	- 包括EV_CLEAR，EV_DISABLE（暂时禁用事件），NOTE_LOWAT，EV_EOF，可用数据数量，错误代码等各种kqueue功能的支持;
	- 支持各种epoll功能，包括EPOLLRDHUP（Linux 2.6.17+，glibc 2.8+）和EPOLLEXCLUSIVE（Linux 4.5+，glibc 2.24+）;
	- sendfile（FreeBSD 3.1+，Linux 2.2+，macOS 10.5+），sendfile64（Linux 2.4.21+）和sendfilev（Solaris 8 7/01 +）支持;
	- 文件AIO （FreeBSD 4.3+，Linux 2.6.22+）;
	- DIRECTIO （FreeBSD 4.4+，Linux 2.4+，Solaris 2.6+，macOS）;
	- 接受过滤器（FreeBSD 4.1+，NetBSD 5.0+）和TCP_DEFER_ACCEPT（Linux 2.4+） 支持 ;
	- 10,000个不活动的HTTP保持连接需要大约2.5M内存;
	- 数据复制操作保持在最低限度。

- 经测试的操作系统和平台
	- FreeBSD 3 - 11 / i386; FreeBSD 5 - 11 / amd64;
	- Linux 2.2 - 4 / i386; Linux 2.6 - 4 / amd64; Linux 3 - 4 /armv6l，armv7l，aarch64，ppc64le;
	- Solaris 9 / i386，sun4u; Solaris 10 / i386，amd64，sun4v;
	- AIX 7.1 / powerpc;
	- HP-UX 11.31 / ia64;
	- macOS / ppc，i386;
	- Windows XP，Windows Server 2003。

.. note:: Wikipedia

Nginx的（/ ˌ ɛ Ñ dʒ ɪ Ñ ɛ ķ 小号 / EN -jin- EKS）（程式化为NGINX，NGiИX或nginx的）是一种网络服务器，其也可以被用作反向代理，负载平衡器和HTTP缓存。该软件由Igor Sysoev创建，并于2004年首次公开发布。[8]同名公司于2011年成立，以提供支持。[9]

Nginx是免费的开放源代码软件，根据类BSD许可条款发布。很大一部分Web服务器使用NGINX，[10]经常作为负载均衡器。[11]
