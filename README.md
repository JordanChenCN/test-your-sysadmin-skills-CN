# 一个锻炼英文和复习SA的小项目
部分翻译自https://github.com/trimstray/test-your-sysadmin-skills/blob/master/README.md

---

## 基础知识

### 简单的问题
- 你这周学习什么了吗?
- 你在系统管理领域最感兴趣的是什么?
- 你最近经历了什么技术上的挑战以及你是怎么解决的呢?
- 介绍下你最后完成的一个重要项目?
- 你对任何开源项目有贡献吗?
- 介绍下你的homelab的设置?(PS:homelab可以理解为家用的服务器,上面装有常用网络服务)
- 你最骄傲的个人成就是什么?
- 你犯过最大的错误是什么?
- 你最喜欢的类unix系统是什么?
- 你是如何管理你的知识库的(比如wiki之类)?
- 你每天的新闻来源是(系统管理,信息安全方面或其他方面)?
- 你和开发人员是怎么互动的:各管各的还是互相合作?
- 如果你正在采访我,你有什么想问的,前提是我非常擅长面对非一般的状况?

## 基本知识

### :diamond_shape_with_a_dot_inside: 初级系统管理员

###### 系统方面的问题

<details>
<summary><b>Linux的发行版有哪些?你最喜欢哪个,为什么?</b></summary><br>

- Red Hat Enterprise Linux
- Fedora
- CentOS
- Debian
- Ubuntu
- Mint
- SUSE Linux Enterprise Server (SLES)
- SUSE Linux Enterprise Desktop (SLED)
- Slackware
- Arch
- Kali
- Backbox

我最喜欢的Linux发行版:

- **Arch Linux**, 提供了一个友好的最小化基础系统,并可以在该基础上构建自定义操作系统.它还有个优点是拥有Arch User Repository (AUR),结合它的官方二进制仓库后可能是所有发行版中拥有最多仓库的系统.它的打包程序也很简单,所以如果安装包在官方仓库和AUR中都没有的话,自己制作一个也很简单.

- **Linux Mint**, 基于Ubuntu的LTS版本构建,但有一些桌面环境不同的版本,比如Cinnamon,MATE和Xfce.Mint相当优美,它的美感非常吸引人,我尤其喜欢它的新图标主题,虽然我相当讨厌它的GTK+主题(对我来说太平淡了).我还在最新的Mint 19版本中发现了一个bug,并在两周前在他们的论坛上寻求帮助,但是至今还没有收到任何回复,让我很恼火.

- **Kali Linux**, 基于Debian的Linux发行版,常用于高级渗透测试和安全审计.Kali有数百种工具来进行各种信息安全任务,比如渗透测试,安全研究,计算机取证和逆向工程.

参考文档：
- [List of Linux distributions](https://en.wikipedia.org/wiki/List_of_Linux_distributions)
- [What is your favorite Linux distro and why?](https://www.quora.com/What-is-your-favorite-Linux-distro-and-why)

</details>

<details>
<summary><b><s>GNU/Linux和UNIX的不同之处有哪些?</s></b></summary><br>

参考答案：

<b>UNIX</b> - 只有大公司被允许使用UNIX的版权和名称.IBM AIX，Sun Solaris，以及HP-UX都是UNIX操作系统.大多数UNIX操作系统都是商业化的.
- 考虑到UNIX操作系统的完整性,它的所有内容都来自同一个厂商.
- 大多数类UNIX操作系统都是收费的.
- UNIX操作系统有它自己的防火墙软件.
- UNIX支持的文件系统为jfs,gpfs (AIX),jfs,gpfs (HP-UX),jfs,gpfs (Solaris).

<b>GNU/Linux</b>是UNIX的克隆,但是如果基于可移植操作系统接口标准考虑的话,那么Linux也能视为UNIX.
- Linux是一种内核,但是也有人认为Linux是操作系统的名称,Linux内核是Linux系统的一部分.
- Linux是免费的,你可以从网上下载或基于GNU许可重新开发发行.
- 所有Linux发行版都包括了GUI系统,GNU应用,安装和管理工具,GNU c/c++ compilers,编辑工具(vi),以及可选的应用程序:OpenOffice,Firefox等.
- Linux自带基于firewall的开源Netfilter和IPTables来保护你的服务器和桌面免受黑客入侵破解.
- Linux默认支持使用ext3或ext4文件系统.

参考文档：
- [The Great Debate: Is it Linux or GNU/Linux?](https://www.howtogeek.com/139287/the-great-debate-is-it-linux-or-gnulinux/)
- [Is It Linux or GNU/Linux?](https://www.linuxjournal.com/content/it-linux-or-gnulinux)

</details>

<details>
<summary><b><s>Linux和UNIX的共同之处有哪些？</s></b></summary><br>

- GUI,文件,以及桌面管理(KDE,Gnome)
- Shells(ksh,csh,bash)
- 可选的办公应用:OpenOffice.org等
- 开发工具:perl,php,python，GNU c/c++ compilers等
- Posix 接口

</details>

<details>
<summary><b><s>什么是Linux，并解释下它的组成部分？</s></b></summary><br>

Linux操作系统包括以下3部分：

- <b>kernel</b>：Linux是一个免费开源的单片内核，负责为用户给管理硬件资源。
- <b>System Library（系统库）</b>：应用程序通过使用系统库来访问内核功能，它扮演着非常重要的角色。
- <b>System Utility（系统调用）</b>：系统调用程序用来执行特定的和个别层面的任务。

</details>

<details>
<summary><b>Unix,Linux,BSD和GNU之间的区别？</b></summary><br>

GNU并不是系统，它更多的是一套管理在创建系统时诞生的一系列自由软件工具的规则或协议，所以GUN工具基本上都是为了符合这个开放软件的标准而重写的已经存在的新的工具版本，GNU/Linux集合了这些工具和Linux内核组成了一个完整的操作系统，但是还有其他“GNU”，比如：GNU/Hurd。

Unix和BSD是POSIX的旧的实现，从各方面来说都是“闭源”的。Unix通常是完全封闭的源代码，但在风格上和Linux一样多（不亚于）。BSD通常也不是开放的，但是它的发行版是开放的。BSD的许可也可以商用，其限制远远少于更开放但限时的许可。

Linux是这四个中最新的。严格来说，它就是个“内核”；但是，一般来说，当它集合了GNU工具和一些其他核心组件时，它就是一个完整操作系统。

他们的主要差异是它们的理念。Unix,Linux和BSD通过不同的理念实现，但它们都属于POSIX，基本是通用的。它们可以用不同方式解决相同的问题，所以除了理念不同和实现POSIX标准方式不同外，几乎没有区别。

更多信息建议阅读有关GNU,Linux,BSD和UNIX起源的文章。虽然这些文章更倾向于个人的理解，但可以让你更好的了解GNU,Linux,BSD和UNIX的差异。

参考文档:
- [What is the difference between Unix, Linux, BSD and GNU? (original)](https://unix.stackexchange.com/questions/104714/what-is-the-difference-between-unix-linux-bsd-and-gnu)
- [The Great Debate: Is it Linux or GNU/Linux?](https://www.howtogeek.com/139287/the-great-debate-is-it-linux-or-gnulinux/)

</details>

<details>
<summary><b>什么是CLI</b></summary><br>

<b>CLI</b>是Command Line Interface的缩写。命令行是管理系统最有用的方式之一。在Linux中，CLI就是这个让用户输入命令完成任务的接口，CLI非常强大，但要避免输错。

参考文档：
- [Command Line Interface Definition](http://www.linfo.org/command_line_interface.html)

</details>

<details>
<summary><b>你最喜欢哪个shell，为什么？</b></summary><br>

BASH是我的最爱。它很棒，非常方便，我喜欢它的语法，它的输出输入重定向语法（<code>>></code>, <code><< 2>&1</code>, <code>2></code>, <code>1></code>, etc）和C++差不多，对我更合适。

我也喜欢ZSH，它比BASH更容易定制。它有很棒的Oh-My-Zsh框架，基于tab的强大的上下文联系，模式匹配/globbing on steroids（不懂），可加载模块以及更多。

参考文档：
- [Comparison of command shells](https://en.wikipedia.org/wiki/Comparison_of_command_shells)

</details>

<details>
<summary><b><s>描述下类Unix系统中的root账号？</s></b></summary><br>
  
<b>root</b>是系统管理员账号，它有系统的全部控制权限（是unix系统中权限最大的账号）。root没有强加的安全限制，这意味着它很容易就能执行管理权限。root的UID总是0。

</details>

<details>
<summary><b>如何获取登陆用户列表？</b></summary><br>
 
需要登陆用户的摘要信息，包括每个登陆的用户名，用户所属终端，登陆的日期时间，以及登陆连接的IP地址，输入：
```bash
# It uses /var/run/utmp and /var/log/wtmp files to get the details.
who
```

需要详细的信息，包括用户名，终端，登陆源IP，登陆时间，IDLE时间，cpu处理周期，cpu作业周期，以及目前正在运行的命令，输入：
```bash
# It uses /var/run/utmp, and their processes /proc.
w
```

显示最后登陆的用户列表也很重要，输入：

```bash
# It uses /var/log/wtmp.
last
```

参考文档：
- [4 Ways to Identify Who is Logged-In on Your Linux System](https://www.thegeekstuff.com/2009/03/4-ways-to-identify-who-is-logged-in-on-your-linux-system/)

</details>

<details>
<summary><b>如何在后台运行命令？</b></summary><br>

你可以通过在要运行的命令后面添加```&```来让该命令在后台运行。比如你想在后台下载一些文件：

```bash
wget https://url-to-download.com/download.tar.gz &
```

当你执行上述命令会有以下输出：

```bash
[1] 2203
```

1是job的序号，2203是job的PID。

你可以通过以下命令来查看在后台运行的job：

```bash
jobs
```

当你在后台执行job时会有一个PID，你可以通过以下命令来停止该job，将PID替换为job的PID：

```bash
kill PID
```

当你只有一个在后台运行的job，你可以通过以下命令来将job前台化：

```bash
fg
```

当你有复数个在后台运行的job，你可以通过把```#```替换为job的序号来将任何job前台化：

```bash
fg %#
```

参考文档：

- [How do I run a Unix process in the background?](https://kb.iu.edu/d/afnz)
- [Job Control Commands](http://tldp.org/LDP/abs/html/x9644.html)

以下为译者补充：
  
- <b>nohup</b>命令可以将程序以忽略挂起信号的方式运行起来：
```bash
nohup command >file 2>&1 &
```

- <b>screen</b>命令，详见[screen命令](http://man.linuxde.net/screen)

</details>

<details>
<summary><b><s>什么是UID和GID？</s></b></summary><br>
  
UID和GID是用户和组的数字标识符。类Unix操作系统通过一个称为用户标识符的数值来标识内核中的用户，这个标识符经常缩写为用户ID或UID。UID以及组标识符（GID）和其他访问控制标准一起决定了用户可以访问系统的哪些资源。

</details>

<details>
<summary><b>当生效用户是root，但实际用户ID是你的名字时意味着什么？</b></summary><br>

实际用户ID是你启动进程的用户，有效用户ID是由操作系统来决定你是否被允许执行某些操作（大多数情况下，偶有例外）。

当你登陆后，shell通过password文件同时把实际和有效用户ID设定为同一值。

比如，你执行了setuid(一个函数)，并且没有用其他（例如root）用户运行，那么setuid程序做了以下操作：

setuid会获取你的实际id（基于你是程序所有者）和文件所有者的有效用户（例如root）。

当passw的权限如下：

```bash
-rwsr-xr-x 1 root root 45396 may 25  2012 /usr/bin/passwd
```

当user2想修改密码时，执行`/usr/bin/passwd`。

**RUID**会变为user2但是程序的**EUID**会变为root。

user2用passwd只能来修改它自己的密码，因为passwd会检查**RUID**是不是user2。如果**RUID**不是root的话，passwd被限制只能修改实际用户的密码。

因为passwd命令需要把结果写入`/etc/passwd` 和/或 `/etc/shadow`，所以执行passwd时**EUID**是root是必须的。

参考文档：

- [Difference between Real User ID, Effective User ID and Saved User ID? (original)](https://stackoverflow.com/questions/30493424/what-is-the-difference-between-a-process-pid-ppid-uid-euid-gid-and-egid)
- [What is the difference between a pid, ppid, uid, euid, gid and egid?](https://stackoverflow.com/questions/30493424/what-is-the-difference-between-a-process-pid-ppid-uid-euid-gid-and-egid)

</details>

<details>
<summary><b>为什么admin用户用root执行所有命令是不好的？</b></summary><br>

因为：

- **愚蠢的**：容易犯粗心的错误。当你想以任何可能有害的方式来更改系统时，你需要使用sudo，它可以让你在输密码时能暂时想想是不是犯错了。

- **安全性**：不知道admin用户的登陆密码时更难被入侵。root意味着你有了一半的工作组管理员凭据。

- **不是必须的**：如果你觉得当`sudo`过期，你不得不输入多次密码来用root执行一系列命令很麻烦的话，你只需要执行`sudo -i`就可以转换为root了。当你想用pipes执行一些命令时，可以使用`sudo sh -c "command1 | command2"`。

- **你可以始终在恢复控制台使用**：恢复控制台可以让你的系统从一个重大失误中恢复，或者修复一个由程序引起的问题（你还是得用`sudo`）。

参考文档：

- [Why is it bad to log in as root? (original)](https://askubuntu.com/questions/16178/why-is-it-bad-to-log-in-as-root)

</details>

<details>
<summary><b>什么命令可以用来回顾系统启动时的信息？</b></summary><br>

<code>dmesg</code>可以用来回顾系统启动时的信息。这个命令可以显示在内核ring buffer中的系统信息。启动完成后我们可以马上执行该命令来查看启动信息。ring buffer是一种固定大小的缓冲区，任何添加到其中的新数据都会覆盖之前的旧数据。
 
</details>

<details>
<summary><b>什么是交换空间？</b></summary><br>
  
当物理内存（RAM）用完了才使用交换空间。如果系统需要更多内存资源而RAMy用完了，那么内存中的非活动页面将移到交换空间中。虽然交换空间可以帮到一些内存小的机器，但它不能被当作RAM的替代品，因为交换空间位于硬盘上，访问速度比物理内存慢很多。

</details>

<details>
<summary><b>如何检查内存和cpu状态？</b></summary><br>

你可以同时使用`top/htop`。<code>free</code>和<code>vmstat</code>命令可以分别显示物理和虚拟内存的状态。<code>sar</code>命令可以显示cpu利用率和其他数据（但是大多数系统m并没有安装`sar`）。

</details>

<details>
<summary><b>什么是负载平均值？</b></summary><br>
Linux负载平均值就是系统负载平均值，它将需要在系统上运行的线程（任务）显示为一个运行和等待的线程的平均值。这个需求量可以大于系统当前能处理的需求量。大多数工具显示了1，5，15分钟的平均值。

一些解读：

- 如果平均值是0.0，那么系统是空闲状态。
- 如果1分钟平均值大于5或15分钟平均值，那么负载在增加中。
- 如果1分钟平均值小于5或15分钟平均值，那么负载在减少中。
- 如果负载值大于cpu数量，那么可以会遇到性能问题（不一定)。

</details>

<details>
<summary><b>如何创建分区和文件系统？</b></summary><br>

1) <code>fdisk</code>或<code>gparted</code> - 创建一个新的分区
2) <code>mkfs</code> - 创建一个新的文件系统

</details>

<details>
<summary><b>系统日志的作用？</b></summary><br>

日志在文件系统中有专用的区域，跟踪了系统所有变化。由于日志存在，当系统崩溃时，可以降低文件系统损坏的可能。

</details>

<details>
<summary><b>类Unix的权限有哪些？</b></summary><br>
  
- <b>Read</b>: 用户可以读文件或列出目录<br>
- <b>Write</b>: 用户可以写文件或在目录中新增文件<br>
- <b>Execute</b>: 用户可以运行文件或在目录中查找特定文件

</details>

<details>
<summary><b>Linux中的密码文件在哪？</b></summary><br>
  
Linux密码存在<b>/etc/shadow</b>文件中，它们被salt加密并根据不同的发行版使用了不同的算法。

</details>

<details>
<summary><b>在Linux/UNIX中如何修改目录和子目录中的文件权限？</b></summary><br>
  
把所有目录改成755（drwxr-xr-x）权限:

<code>
find /opt/data -type d -exec chmod 755 {} \;
</code><br><br>

把所有文件改成644 (-rw-r--r--)权限：<br>

<code>
find /opt/data -type f -exec chmod 644 {} \;
</code><br><br>

</details>

<details>
<summary><b>什么是重定向？</b></summary><br>
  
重定向是一个简单的过程，它允许你将数据从一个输出定向到另一个输出。你也可以用重定向把输出作为输入定向到另外一个程序。

</details>

<details>
<summary><b>grep命令是什么？</b></summary><br>
  
<code>grep</code>搜索文件模式。如果你要在另一个命令输出中匹配一个特定的模式，grep可以让相关行高亮。grep命令可以用来搜索日志文件，特定的进程等等。

</details>

<details>
<summary><b>描述下查看文件内容的命令？</b></summary><br>

- <b>head</b>: 查看文件首部的内容.<br>
- <b>tail</b>: 查看文件尾部的内容，和head命令相反.<br>
- <b>cat</b>: 查看，创建，串联文件.<br>
- <b>more</b>: 以pager形式在终端窗口中展示文本.<br>
- <b>less</b>: 用于向后查看文本并提供单行移动.

</details>

<details>
<summary><b>描述以下Posix信号：SIGHUP，SIGINT，SIGKILL和SIGTERM？</b></summary><br>
  
- <b>SIGHUP</b> - 当进程控制终端关闭时会发送SIGHUP信号给进程。它最初被设计用于通知进程的串行线路丢弃（挂起）。很多守护进程收到这个信号时会重新加载配置文件和重开日志文件而不是退出。<br>
- <b>SIGINT</b> - 当用户希望中断进程时通过控制终端发送SIGINT信号给进程。通常通过按下Ctrl+C发起，但在有些系统上，"delete"和"break"也有同样功能。<br>
- <b>SIGKILL</b> - 当用户需要立刻终止进程时发送SIGKILL信号给进程（kill）。与SIGTERM和SIGINT相反，该信号无法被捕捉或忽略，同时收到该信号的进程也无法执行任何清理操作。<br>
- <b>SIGTERM</b> - 需要请求进程终止时发送SIGTERM信号给进程。和SIGKILL不同，它会被进程捕获，解析或忽略。SIGTERM信号可以让进程优雅地释放资源，保存状态然后终止。SIGTERM和SIGINT几乎相同。

</details>

<details>
<summary><b><code>rm</code> and <code>rm -rf</code>之间的区别？</b></summary><br>

<code>rm</code>删除文件，<code>-rf</code>有以下2个作用<br>

- <code>-r</code>以递归方式删除目录及其内容<br>
- <code>-f</code>禁用提示，忽略不存在的文件

</details>

<details>
<summary><b>如何列出archive.tgz的内容并提取一个文件？</b></summary><br>

```bash
tar tf archive.tgz
tar xf archive.tgz filename
```

</details>

<details>
<summary><b>如何同步2个本地目录？</b></summary><br>

在同一个系统上把dir1的内容同步到dir2中，输入：

```bash
rsync -av --progress --delete dir1/ dir2
```

- <code>-a, --archive</code> - 存档模式
- <code>--delete</code> - 删除目标目录中的无关文件
- <code>-v, --verbose</code> - 详细模式
- <code>--progress</code> - 传输时显示进度

</details>

<details>
<summary><b>如何快速备份一个文件？</b></summary><br>

```bash
cp filename{,.orig}
```

</details>

<details>
<summary><b>如何查找大于20m的文件?</b></summary><br>

```bash
find / -type f -size +20M
```

</details>

<details>
<summary><b><code>sudo su -</code>和<code>sudo su</code>的区别是什么?</b></summary><br>

<code>su -</code>会在切换用户后再登陆shell，可以重置大多数环境变量，来提供一个干净的基础。

<code>su</code>只是切换用户，提供一个环境变量和之前的用户几乎一样的shell。

</details>

<details>
<summary><b>如何查找系统中在过去60分钟修改过的文件?</b></summary><br>

```bash
find / -mmin -60 -type f
```

</details>

<details>
<summary><b>为什么保留系统中的旧日志?</b></summary><br>

旧日志在调查系统问题时很重要。

</details>

<details>
<summary><b>什么是增量备份?</b></summary><br>

增量备份是一种只复制自上次备份以来更新的文件的备份方式。

</details>

<details>
<summary><b>什么是RAID?什么是RAID0,RAID1,RAID5,RAID6,RAID10?</b></summary><br>

<b>RAID</b> (Redundant Array of Inexpensive/Independent Disks)是一种提高数据存储性能和/或可靠性的技术。

- <b>RAID0</b>：也成为磁盘条带化，是一种将文件分割并将数据保存在RAID组中的所有磁盘驱动器的技术，没有任何冗余措施。

- <b>RAID1</b>：一种通过把数据写入2个磁盘来提高安全性的流行磁盘系统，也叫镜像化。RAID1不会提高写性能，但读性能约等于每个磁盘性能的和。当其中一个磁盘驱动器发生故障后，还可以使用另一个磁盘驱动，并在手动更换了故障的驱动器后，RAID控制器会把正常的工作驱动器上的全部内容复制到新的驱动器上。

- <b>RAID5</b>：一种通过计算奇偶校验数据来提高安全性，通过把数据分布在三个或更多驱动器的来提高速度（条带化）的磁盘系统。当单个驱动器发生故障时，可以读取计算分布式奇偶校验数据来恢复损坏盘中的数据。

- <b>RAID6</b>：RAID6通过新增一块奇偶校验盘来扩展RAID5。它至少需要4块磁盘，并能在2块盘同时发生故障时继续读写操作。RAID6对读操作没有性能损失，但由于计算奇偶校验的开销，在写操作上会有性能损失。

- <b>RAID10</b>：即RAID1+0，是一种结合了磁盘镜像化和磁盘条带化来保护数据的RAID配置。它至少需要4块盘，并把镜像的数据条带化。只要每对镜像化的磁盘中有一个正常工作，数据就可以恢复。但如果同一镜像对中的2块磁盘都发生了故障，那么由于条带化中没有奇偶校验，所有数据都会丢失。

</details>

<details>
<summary><b>如何指定和修改用户的默认组?</b></summary><br>

<code>useradd -m -g initial_group username</code>

<b>-g/--gid:</b>定义了用户初始登陆组的组名或组号。如果用这个参数指定了组名或组号，那组必须是已存在的。如果没有使用该参数，那么将根据/etc/login.defs文件中的USERGROUPS_ENAB变量来决定useradd命令的结果。（USERGROUPS_ENAB yes）时默认创建一个与用户名相同的组，GID也等于UID。

</details>

<details>
<summary><b>为什么要把服务器放在机柜中?</b></summary><br>

- 保护硬件
- 工作区组织化
- 更好地电源管理
- 更整洁的环境

</details>

###### 网络问题

<details>
<summary><b>通过http监控发现网站挂了，但可以telnet通端口，如何解决改问题？</b></summary><br>

我会通过ssh连接到web服务器，然后查看相关日志文件，找出问题再解决问题。

</details>

<details>
<summary><b>SMTP, FTP, DNS, DHCP 和 SSH的默认端口是什么？</b></summary><br>

<table style="width:100%">
  <tr>
    <th>SERVICE</th>
    <th>PORT</th>
  </tr>
  <tr>
    <td>SMTP</td>
    <td>25</td>
  </tr>
  <tr>
    <td>FTP</td>
    <td>20：传输数据；21：保持连接</td>
  </tr>
  <tr>
    <td>DNS</td>
    <td>53</td>
  </tr>
  <tr>
    <td>DHCP</td>
    <td>67/UDP：DHCP服务端；68/UDP：DHCP 客户端</td>
  </tr>
  <tr>
    <td>SSH</td>
    <td>22</td>
  </tr>
</table>

</details>

<details>
<summary><b>当你在浏览器中输入api.example.com并回车发生了什么?</b></summary><br>

首先，查询浏览器自己的DNS缓存，查不到时请求操作系统去解析域名。操作系统也有自己的DNS缓存，解析失败时再向操作系统配置的DNS服务器请求。操作系统配置的DNS服务器一般是由路由器中的DHCP服务配置的，而DHCP服务配置的基本上是从internet网关配置的ISP的DNS服务器。如果路由器有自己的DNS服务器，那一般也会有缓存，否则只要发现操作系统没有DNS缓存，就直接向ISP的DNS服务器请求解析。

</details>

<details>
<summary><b>如何检查路由和路由表?</b></summary><br>
  
可以使用<code>netstat -nr</code>, <code>route -n</code>或<code>ip route show</code>命令来查看默认路由和路由表。

</details>

<details>
<summary><b>127.0.0.1和localhost之间的区别是什么?</b></summary><br>
  
嗯，最大的不同就是你还是不得不在某处查找localhost。

如果你使用<code>127.0.0.1</code>，那么软件会直接使用这个IP地址。code>gethostbyname</code>（系统函数）的某些实现会检查dotted format（可能是等效的IPv6格式）而不再查找。

不然的话，必须解析主机名，并且不能保证你的hosts文件能解析正确，因为localhost可能改成一个完全不同的IP地址。

这意味着，在某些系统上，可以绕过本地的hosts文件。<code>host.conf</code>文件在Linux和多数Unices上可以控制这个。

如果你使用unix域套接字，速度会比TCP/IP稍快（系统开销小）。Windows默认使用TCP/IP，而Linux根据你的选择来分，如果使用localhost，为unix域套接字，如果使用<code>127.0.0.1</code>，则是TCP/IP。

参考文档：

- **[What is the difference between 127.0.0.1 and localhost?](https://stackoverflow.com/questions/7382602/what-is-the-difference-between-127-0-0-1-and-localhost)**
- **[localhost vs. 127.0.0.1](https://stackoverflow.com/questions/3715925/localhost-vs-127-0-0-1)**

</details>

<details>
<summary><b>如何用CLI来解析域名（使用外部DNS服务器）?</b></summary><br>
  
```bash
# with host command:
host domain.com 8.8.8.8
# with dig command:
dig @9.9.9.9 google.com
# with nslookup command:
nslookup domain.com 8.8.8.8
```

</details>

<details>
<summary><b>如何用<code>telnet</code>或<code>nc</code>测试端口能否连通?</b></summary><br>


```bash
# with telnet command:
telnet code42.example.com 5432
# with nc (netcat) command:
nc -vz code42.example.com 5432
```

</details>

<details>
<summary><b>为什么要避免用telnet远程管理系统?</b></summary><br>
  
telnet使用了很不安全的连接来通信。它用纯文本格式在网络上发送数据，任何人都可以用网络工具轻松找到密码。

对telnet来说，用纯文本格式来传递登陆凭证意味着在你的网路上运行嗅探器窃听telnet登陆会话的任何人都能在几秒钟找到关键信息来控制你的设备。

</details>

<details>
<summary><b><code>wget</code>和<code>curl</code>之间有什么不同?</b></summary><br>
  
主要区别：wget可以以递归方式下载而curl不可以。wget只支持命令行，curl支持FTP，FTPS，HTTP，HTTPS，SCP，SFTP，TFTP，TELNET，DICT，LDAP，LDAPS，FILE，POP3，IMAP，SMTP，RTMP和RTSP。

</details>

<details>
<summary><b>什么是SSH以及它是如何工作的?</b></summary><br>

SSH代表安全的shell。它是一种协议，允许你从通过服务器A跳转到服务器B的shell会话，然后和服务器B进行交互。要建立一个SSH连接，需要远程服务器（B）运行ssh服务端进程并且用户的计算机（A）运行ssh客户端。ssh服务端和客户端都监听一个特定的网络端口（默认是22），并对连接请求进行身份验证，当用户提供了正确的凭据时生成相应的工作环境。
  
</details>

<details>
<summary><b>什么是包过滤器以及它是如何工作的?</b></summary><br>  
  
包过滤器是一种防火墙技术，它控制网络访问的方式是：监控传入和传出的包并根据包中的源地址，目的地址，协议，端口等决定是否让包传递到系统网络或直接丢弃。
  
</details>

<details>
<summary><b>什么是代理以及它是如何工作的?</b></summary><br>    
  
代理服务器是在2台终端设备之间充当中介的一台专用计算机或一种软件系统，它可以将用户或客户端的请求发送到另一台服务器中。
  
</details>

<details>
<summary><b>路由和网关之间的区别是什么?什么是默认路由?</b></summary><br>      
  
路由和网关都用于调节2个或更多独立网络之间的网络流量。网关调节的是2个完全不同的网络之间的流量，而路由调节的是相似网络之间的流量。

默认网关作为一个接入点或IP路由将信息发送到另一个网络或互联网中。除非应用指定另一个网关，默认使用默认网关。

网关是计算机网络中的节点（路由），是发送或接受网络中的数据的关键。多亏了网关，我们能互相通信和发送数据。
  
</details>

<details>
<summary><b>解释以下DNS的每个记录的功能：SOA, PTR, A, MX, 以及CNAME?</b></summary><br>      
  
DNS记录实质上是映射的文件，用来告诉DNS服务器每个域名和其对应的IP地址，以及如何处理发送给每个域名的请求。绝大部分DNS的记录配置使用以下记录类型：A, AAAA, CNAME, MX, PTR, NS, SOA, SRV, TXT, 和NAPTR。

- <b>SOA</b> - 起始授权机构记录
- <b>A</b> - 域名指向ip地址记录
- <b>AAAA</b> - 域名指向ipv6地址记录
- <b>CNAME</b> - 域名指向另一个域名记录
- <b>MX</b> - 域名指向邮件服务器地址记录
- <b>NS</b> - 域名服务器记录
- <b>PTR</b> - 反向解析记录

</details>

<details>
<summary><b>可以用于最多30台设备的最小IPv4子网掩码是什么?</b></summary><br>      

最大30台设备的话是/27 - 或子网掩码<code>255.255.255.224</code>

</details>

<details>
<summary><b>简介web各种响应码?</b></summary><br>      


- <b>1xx</b> - 信息响应 - 传递传输协议级别的信息
- <b>2xx</b> - 成功 - 表示客户端的请求已成功接受
- <b>3xx</b> - 重定向 - 表示客户端需要一些其他操作才能完成其请求
- <b>4xx</b> - 客户端错误 - 这类错误码表示客户端有问题
- <b>5xx</b> - 服务端错误 - 这类错误码表示服务端有问题

</details>

###### Devops问题

<details>
<summary><b>什么是版本控制?</b></summary><br>      

版本控制是一个根据时间来记录文件或文件夹变化的系统，它可以让你在以后回调特定的文件版本。版本控制系统包括一个集中共享仓库，用来记录协作者提交的对文件或文件夹的更改。以下为版本控制的作用。

版本控制可以让你：

- 将文件恢复为之前的状态
- 将整个项目恢复为之前的状态
- 根据时间来比较更改内容
- 查找可能导致问题的最后的修改是谁写的
- 谁，什么时候提出了什么问题

</details>

<details>
<summary><b>简述一些Git基本命令?</b></summary><br>      

- <code>git init</code> - 创建一个新的本地仓库
- <code>git commit -m "message"</code> - 提交更改
- <code>git status</code> - 显示工作目录和暂存区的状态
- <code>git push origin master</code> - 把更改推送到远程仓库项目的master分支

</details>

###### 网络安全问题

<details>
<summary><b>什么是错误的安全配置?</b></summary><br>

当设备/程序/网络的配置方式可以被攻击者利用时，就是一种错误的安全配置。简单例子：使用默认的用户名/密码，简单的设备账户名等。

</details>

### :diamond_shape_with_a_dot_inside: 中级系统管理员

###### 系统问题

<details>
<summary><b>简述Linux启动流程。</b></summary><br>
  
<b>BIOS</b>: BIOS的全称为Basic Input or Output System，它先执行系统完整性检查，然后在MBR中查找并执行bootloader。<br>

<b>MBR</b>: MBR全称为Master Boot Record，MBR记录了有关GRUB的信息，并执行和加载该GRUB。<br>

<b>GRUB</b>: GRUB全称为Grand Unified Bootloader。如果系统上安装了多个内核镜像，那么需要选择加载哪个内核。<br>

<b>Kernel</b>: 内核挂载根文件系统并执行<code>/sbin/init</code>程序。<br>

<b>Init</b>: Init程序检查<code>/etc/inittab</code>文件并决定系统运行级别。一共由7个运行级别，从0-6。Init识别默认的运行级别后加载对应的程序。<br>

<b>Runlevel programs</b>: 根据设定的默认运行级别，系统执行对应的程序。

</details>

<details>
<summary><b>什么是UID为0叫<code>toor</code>的账户?是被入侵了吗?</b></summary><br>

<code>toor</code>是一个超级账户root的"替代"，由root反着拼写而来。它可以在非标准的shell上使用，所以root就能在默认的shell上直接使用。

因为shells不是基础发行版的一部分，而是通过端口或安装包默认安装在不同的文件系统中
  
  
  
  
  
