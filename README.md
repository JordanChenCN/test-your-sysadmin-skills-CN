# 一个锻炼英文和复习SA的小项目
部分翻译自https://github.com/trimstray/test-your-sysadmin-skills/blob/master/README.md

---

## 基础知识

### :diamond_shape_with_a_dot_inside: 简单的问题
- 你这周学习什么了吗?
- 你在系统管理领域最感兴趣的是什么?
- 你最近经历了什么技术上的挑战以及你是怎么解决的呢?
- 介绍下你最后完成的一个重要项目?
- 你对任何开源项目有贡献吗?
- 介绍下你的homelab的设置?(PS:homelab可以理解为家用的服务器,上面装有常用网络服务)
- 你最骄傲的个人成就是什么?
- 你犯过最大的错误是什么,如果是现在会怎么样处理?
- 在新工作的第一天你会安装哪些软件工具?
- 你是如何管理你的知识库的(比如wiki之类)?
- 你每天的新闻来源是(系统管理,信息安全方面或其他方面)?
- 你的NOC团队有一个新的系统管理员认证预算,你想要什么证书?为什么?
- 你和开发人员是怎么互动的:各管各的还是互相合作?
- 如果你正在采访我,你有什么想问的,前提是我非常擅长处理突发状况?

## 基本知识

### :diamond_shape_with_a_dot_inside: 初级系统管理员

###### 系统方面的问题 (36)

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

参考文档:
- [List of Linux distributions](https://en.wikipedia.org/wiki/List_of_Linux_distributions)
- [What is your favorite Linux distro and why?](https://www.quora.com/What-is-your-favorite-Linux-distro-and-why)

</details>

<details>
<summary><b>Unix,Linux,BSD和GNU之间的区别?</b></summary><br>

GNU并不是系统,它更多的是一套管理在创建系统时诞生的一系列自由软件工具的规则或协议,所以GUN工具基本上都是为了符合这个开放软件的标准而重写的已经存在的新的工具版本,GNU/Linux集合了这些工具和Linu内核组成了一个完整的操作系统,但是还有其他“GNU”,比如:GNU/Hurd.

Unix和BSD是POSIX的旧的实现,从各方面来说都是“闭源”的.Unix通常是完全封闭的源代码,但在风格上和Linux一样多(不亚于).BSD通常也不是开放的,但是它的发行版是开放的.BSD的许可也可以商用,其限制远远少于更开放但限时的许可.

Linux是这四个中最新的.严格来说,它就是个“内核”；但是,一般来说,当它集合了GNU工具和一些其他核心组件时,它就是一个完整操作系统.

他们的主要差异是它们的理念.Unix,Linux和BSD通过不同的理念实现,但它们都属于POSIX,基本是通用的.它们可以用不同方式解决相同的问题,所以除了理念不同和实现POSIX标准方式不同外,几乎没有区别.

更多信息建议阅读有关GNU,Linux,BSD和Unix起源的文章.虽然这些文章更倾向于个人的理解,但可以让你更好的了解GNU,Linux,BSD和Unix的差异.

参考文档:
- [What is the difference between Unix, Linux, BSD and GNU? (original)](https://unix.stackexchange.com/questions/104714/what-is-the-difference-between-unix-linux-bsd-and-gnu)
- [The Great Debate: Is it Linux or GNU/Linux?](https://www.howtogeek.com/139287/the-great-debate-is-it-linux-or-gnulinux/)

</details>

<details>
<summary><b>什么是CLI,并说说你最喜欢的CLI命令,小技巧等?</b></summary><br>

**CLI**是Command Line Interface的缩写.命令行是管理系统最有用的方式之一.

在Linux中,**CLI**就是这个让用户输入命令完成任务的接口,CLI非常强大,但要避免输错.

CLI可以让你操作系统内部组件,并以更精细的方式操作代码.无论使用何种操作系统,它都比GUI提供更强大的灵活性和控制力.你的软件所依赖的许多程序(如Github)也需要在CLI执行一些命令才能运行.

**我最喜欢的命令**

- `screen` - 免费的终端多复用工具,当我用screen开启一个会话,即使途中和终端的连接丢失,该会话还是能在重连后恢复.
- `ssh` - 最有学习价值的命令,我们可以用来做下列操作:
  * 使用`sshfs`挂载网络上的文件系统
  * 转发命令:通过ssh启动一个没有运行`rsync` 守护进程的`rsync` 服务器
  * 在批处理文件中运行:重定向远程命令的输出并在本地批处理文件中使用
- `vi/vim` -  最流行和最强大的文本编辑器,即使处理大文本文件,它的速度也很快
- `bash-completion` - 包括了很多预配置的shell命令补全规则

**小技巧**

- `CTRL + R`:搜索历史命令
- `popd/pushd`:操作目录堆栈
- `CTRL + U`, `CTRL + E`:编辑键盘快捷键
- 自动扩展组合:
  * `!*` - 上个命令的所有参数
  * `!!` - 上个命令的全部
  * `!ssh` - ssh开头的最近的历史命令

参考文档:
- [Command Line Interface Definition](http://www.linfo.org/command_line_interface.html)
- [What is your single most favorite command-line trick using Bash?](https://stackoverflow.com/questions/68372/what-is-your-single-most-favorite-command-line-trick-using-bash/69716)
- [What are your favorite command line features or tricks?](https://unix.stackexchange.com/questions/6/what-are-your-favorite-command-line-features-or-tricks)

</details>

<details>
<summary><b>你最喜欢哪个shell,为什么?</b></summary><br>

**BASH**是我的最爱.它很棒,非常方便,我喜欢它的语法,它的输出输入重定向语法(`>>`, `<< 2>&1`, `2>`, `1>`, etc)和C++差不多,对我更合适.

我也喜欢**ZSH**,它比**BASH**更容易定制.它有很棒的Oh-My-Zsh框架,基于tab的强大的上下文联系,模式匹配/globbing on steroids(不懂),可加载模块以及更多.

参考文档:
- [Comparison of command shells](https://en.wikipedia.org/wiki/Comparison_of_command_shells)

</details>

<details>
<summary><b>如何从命令行获得帮助? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>登录*nix系统后的前5个命令?</b></summary><br>

- `w` - 查看服务器运行时间,登录用户信息,负载等
- `top` - 查看所有运行的进程,并通过cpu,内存等来排序
- `netstat` - 查看服务器上的程序监听的地址和端口
- `df` - 查看文件系统的可用磁盘空间
- `history` - 查看当前用户之前连接时的命令内容

参考文档:

- [First 5 Commands When I Connect on a Linux Server (original)](https://www.linux.com/blog/first-5-commands-when-i-connect-linux-server)

</details>

<details>
<summary><b><code>ls -al</code>输出中的各字段是什么意思?</b></summary><br>

按输出顺序来分别是:

```bash
-rwxrw-r--    1    root   root 2048    Jan 13 07:11 db.dump
```
- 文件权限,
- 链接数量,
- 文件属主,
- 文件属组,
- 文件大小
- 最近修改的时间
- 文件/目录名

文件权限显示如下:

- 第一个字符是`-` 或 `l` 或 `d`,`d`表示是目录,`-`表示是文件,`l`表示是链接文件(或软链接) - 一种特殊的文件类型
- 三个字符一组,共三组,表示文件属主,属组和其他用户的权限:
  - `r` = 读权限
  - `w` = 写权限
  - `x` = 执行权限

例子中的`-rwxrw-r--`表示:

- 一个普通文件(`-`)
- 文件属主可读,可写,可执行(`rwx`)
- 文件属组可读,可写,不可执行(`rw-`)
- 其他用户可读,不可写,不可执行(`r--`)

参考文档:

- [What do the fields in ls -al output mean? (original)](https://unix.stackexchange.com/questions/103114/what-do-the-fields-in-ls-al-output-mean)

</details>

<details>
<summary><b>如何获取登陆用户列表?</b></summary><br>
 
需要登陆用户的摘要信息,包括每个登陆的用户名,用户所属终端,登陆的日期时间,以及登陆连接的IP地址,输入:
```bash
# It uses /var/run/utmp and /var/log/wtmp files to get the details.
who
```

需要详细的信息,包括用户名,终端,登陆源IP,登陆时间,IDLE时间,cpu处理周期,cpu作业周期,以及目前正在运行的命令,输入:
```bash
# It uses /var/run/utmp, and their processes /proc.
w
```

显示最后登陆的用户列表也很重要,输入:

```bash
# It uses /var/log/wtmp.
last
```

参考文档:
- [4 Ways to Identify Who is Logged-In on Your Linux System](https://www.thegeekstuff.com/2009/03/4-ways-to-identify-who-is-logged-in-on-your-linux-system/)

</details>

<details>
<summary><b>在后台运行程序有什么优势,如何在后台运行?</b></summary><br>

最大的优点是当其他进程在后台运行时,你可以在前台同时执行其他任务.因此,在你处理工作时后台可以完成更多任务.你可以通过在要运行的命令后面添加`&`来让该命令在后台运行.

一般把执行时间长且不需要用户交互的应用或命令发送到后台执行,以便我们能在终端上继续工作.

比如你想在后台下载一些文件:

```bash
wget https://url-to-download.com/download.tar.gz &
```

当你执行上述命令会有以下输出:

```bash
[1] 2203
```

1是job的序号,2203是job的PID.

你可以通过以下命令来查看在后台运行的job:

```bash
jobs
```

当你在后台执行job时会有一个PID,你可以通过以下命令来停止该job,将PID替换为job的PID:

```bash
kill PID
```

当你只有一个在后台运行的job,你可以通过以下命令来将job前台化:

```bash
fg
```

当你有复数个在后台运行的job,你可以通过把```#```替换为job的序号来将任何job前台化:

```bash
fg %#
```

参考文档:

- [How do I run a Unix process in the background?](https://kb.iu.edu/d/afnz)
- [Job Control Commands](http://tldp.org/LDP/abs/html/x9644.html)
- [What is/are the advantage(s) of running applications in background?](https://unix.stackexchange.com/questions/162186/what-is-are-the-advantages-of-running-applications-in-backgound)

一些其他的补充:
  
- **nohup**命令可以将程序以忽略挂起信号的方式运行起来:
```bash
nohup command >file 2>&1 &
```

- **screen**命令,详见[screen命令](http://man.linuxde.net/screen)

</details>

<details>
<summary><b>在管理进程前,需要认识进程,这要用到哪些工具? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>为什么admin用户用root执行所有命令是不好的?</b></summary><br>

直接用root执行任何命令都是不好的:

- **愚蠢的**:容易犯粗心的错误.当你想以任何可能有害的方式来更改系统时,你需要使用sudo,它可以让你在输密码时能暂时想想是不是犯错了.

- **安全性**:不知道admin用户的登陆密码时更难被入侵.root意味着你有了一半的工作组管理员凭据.

- **不是必须的**:如果你觉得当`sudo`过期,你不得不输入多次密码来用root执行一系列命令很麻烦的话,你只需要执行`sudo -i`就可以转换为root了.当你想用pipes执行一些命令时,可以使用`sudo sh -c "command1 | command2"`.

- **你可以始终在恢复控制台使用**:恢复控制台可以让你的系统从一个重大失误中恢复,或者修复一个由程序引起的问题(你还是得用`sudo`).

参考文档:

- [Why is it bad to log in as root? (original)](https://askubuntu.com/questions/16178/why-is-it-bad-to-log-in-as-root)
- [What's wrong with always being root?](https://serverfault.com/questions/57962/whats-wrong-with-always-being-root)
- [Why you should avoid running applications as root](https://bencane.com/2012/02/20/why-you-should-avoid-running-applications-as-root/)

</details>

<details>
<summary><b>如何检查内存和cpu状态?</b></summary><br>

你可以同时使用`top/htop`.`free`和`vmstat`命令可以分别显示物理和虚拟内存的状态.`sar`命令可以显示cpu利用率和其它信息统计(但是大多数系统并没有安装`sar`).

参考文档:

- [How do I Find Out Linux CPU Utilization?](https://www.cyberciti.biz/tips/how-do-i-find-out-linux-cpu-utilization.html)
- [16 Linux server monitoring commands you really need to know](https://www.hpe.com/us/en/insights/articles/16-linux-server-monitoring-commands-you-really-need-to-know-1703.html)

</details>

<details>
<summary><b>什么是负载平均值?</b></summary><br>

Linux的**负载平均值**就是"系统负载平均值",它将需要在系统上运行的线程(任务)显示为一个运行和等待的线程的平均值.这个需求量可以大于系统当前能处理的需求量.大多数工具显示了1,5,15分钟的平均值.

这3个值不是不同的CPUs,而是3个时间段(最新的1分钟,5分钟,15分钟)的负载平均值.

**负载平均值**通常也称为"运行队列的平均长度".所以很少有消耗CPU的进程或线程能把**负载平均值**升到1.
如果**负载平均值**小于CPU核心数,那就没啥问题.但如果大于CPU核心数,则表示有些线程/进程会在队列中等待CPU有空闲时运行.

它可以让你了解系统在某些时间段内的状态.由于是平均值,当有突发的高负载后,需要一段时间才能变成0.

一些解读:

- 如果平均值是0.0,那么系统是空闲状态
- 如果1分钟平均值大于5或15分钟平均值,那么负载在增加中
- 如果1分钟平均值小于5或15分钟平均值,那么负载在减少中
- 如果负载值大于cpu数量,那么可以会遇到性能问题(不一定)

参考文档:

- [Linux Load Averages: Solving the Mystery (original)](http://www.brendangregg.com/blog/2017-08-08/linux-load-averages.html)

</details>

<details>
<summary><b>Linux/Unix中的密码文件在哪?</b></summary><br>
  
密码不存储在系统中的任何地方.`/etc/shadow`中存储的是密码哈希后的值.

通过对文本(即密码)执行单向函数算法来创建出该文本的哈希值,从而创建出需要检查的字符串.这个被设计成"不可能"(计算力不够)逆转的过程.

较旧的Unix版本会将加密后的密码和其他信息根据账户存储在`/etc/passwd`中.

新的则在`/etc/passwd`中的相关字段留一个`*`,并使用`/etc/shadow`来储存密码,来确保有人做不需要密码的操作时对密码没有读的权限(`shadow`的保护性比`passwd`更强).

更多信息查看`man crypt`, `man shadow`, `man passwd`.

参考文档:

- [Where is my password stored on Linux?](https://security.stackexchange.com/questions/37050/where-is-my-password-stored-on-linux)
- [Where are the passwords of the users located in Linux?](https://www.cyberciti.biz/faq/where-are-the-passwords-of-the-users-located-in-linux/)
- [Linux Password & Shadow File Formats](https://www.tldp.org/LDP/lame/LAME/linux-admin-made-easy/shadow-file-formats.html)

</details>

<details>
<summary><b>如何递归地修改除了文件的所有目录权限和除了目录的所有文件权限?</b></summary><br>
  
把所有目录改成**755**(`drwxr-xr-x`)权限:

```bash
find /opt/data -type d -exec chmod 755 {} \;
```

把所有文件改成**644**(`-rw-r--r--`)权限:

```bash
find /opt/data -type f -exec chmod 644 {} \;
```

参考文档:

- [How do I set chmod for a folder and all of its subfolders and files? (original)](https://stackoverflow.com/questions/3740152/how-do-i-set-chmod-for-a-folder-and-all-of-its-subfolders-and-files?rq=1)

</details>

<details>
<summary><b>执行命令报错<code>command not found</code>. 该如何查找原因和解决?</b></summary><br>

看起来可能是覆盖了默认的`PATH`环境变量.现有的错误类型表明`PATH`中没有包括`/bin`,这个是命令(包括bash)所在的目录.

可以通过`-x`选项在子shell中调试bash脚本或命令:

```bash
bash --login -x
```

这个命令会显示shell启动时执行的所有的命令和参数.

显示`PATH`变量值也很有用:

```bash
echo $PATH
```

如果显示如下:

```bash
PATH=/bin:/sbin:/usr/bin:/usr/sbin
```

那么大多数命令都能工作 - 然后就可以编辑`~/.bash_profile`(替代 `~/.bashrc`)来修复重置`PATH`.**root**和其他用户的默认`PATH`变量在`/etc/profile`文件中.

参考文档:

- [How to correctly add a path to PATH?](https://unix.stackexchange.com/questions/26047/how-to-correctly-add-a-path-to-path)

</details>

<details>
<summary><b>输入<code>CTRL + C</code>后脚本还在继续运行. 该怎么停止?***</b></summary><br>

待续.

参考文档:

- [How to kill a script running in terminal, without closing terminal (Ctrl + C doesn't work)? (original)](https://askubuntu.com/questions/520107/how-to-kill-a-script-running-in-terminal-without-closing-terminal-ctrl-c-doe)
- [What's the difference between ^C and ^D for Unix/Mac OS X terminal?](https://superuser.com/questions/169051/whats-the-difference-between-c-and-d-for-unix-mac-os-x-terminal)

</details>

<details>
<summary><b>grep命令是什么,如何在同一行中匹配多个字符串?</b></summary><br>
  
`grep`是Unix系列工具,还包括`egrep` and `fgrep`.

`grep`搜索文件模式.如果你要在另一个命令输出中匹配一个特定的模式,`grep`可以让相关行高亮.grep命令可以用来搜索日志文件,特定的进程等等.

匹配多个字符串:

```bash
grep -E "string1|string2" filename
```

或者

```bash
grep -e "string1" -e "string2" filename
```

参考文档:
- [What is grep, and how do I use it? (original)](https://kb.iu.edu/d/afiy)

</details>

<details>
<summary><b>描述下查看文件内容的命令?</b></summary><br>

- **head**: 查看文件首部的内容.
- **tail**: 查看文件尾部的内容,和head命令相反.
- **cat**: 查看,创建,串联文件.
- **more**: 以pager形式在终端窗口中展示文本.
- **less**: 用于向后查看文本并提供单行移动.

参考文档:

- [Viewing text files from the shell prompt](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/4/html/Step_by_Step_Guide/s1-viewingtext-terminal.html)

</details>

<details>
<summary><b>描述以下Posix信号:SIGHUP,SIGINT,SIGKILL和SIGTERM?</b></summary><br>
  
- **SIGHUP** - 当进程控制终端关闭时会发送SIGHUP信号给进程.它最初被设计用于通知进程的串行线路丢弃(挂起).很多守护进程收到这个信号时会重新加载配置文件和重开日志文件而不是退出.
- **SIGINT** - 当用户希望中断进程时通过控制终端发送SIGINT信号给进程.通常通过按下`Ctrl+C`发起,但在有些系统上,"delete"和"break"也有同样功能.
- **SIGKILL** - 当用户需要立刻终止进程时发送**SIGKILL**信号给进程(kill).与**SIGTERM**和**SIGINT**相反,该信号无法被捕捉或忽略,同时收到该信号的进程也无法执行任何清理操作.
- **SIGTERM** - 需要请求进程终止时发送**SIGTERM**信号给进程.和**SIGKILL**不同,它会被进程捕获,解析或忽略.**SIGTERM**信号可以让进程优雅地释放资源,保存状态然后终止.**SIGTERM**和**SIGINT**几乎相同.

参考文档:

- [POSIX signals](https://dsa.cs.tsinghua.edu.cn/oj/static/unix_signal.html)
- [Introduction To Unix Signals Programming](http://titania.ctie.monash.edu.au/signals/)

</details>

<details>
<summary><b><code>kill</code>命令的作用?</b></summary><br>

在Unix和类Unix操作系统中,`kill`是一个向进程发送信号的命令.默认发送的是终止信号,请求进程退出.但是`kill`算是一种误称,发送的信号不一定是终止信号.

参考文档:

- [Mastering the "Kill" Command in Linux](https://www.maketecheasier.com/kill-command-in-linux/)

</details>

<details>
<summary><b><code>rm</code>和<code>rm -rf</code>之间的区别?</b></summary><br>

`rm`删除文件,`-rf`有以下2个作用:

- `-r`, `-R`, `--recursive`:以递归方式删除目录及其内容,包括隐藏文件和子目录.
- `-f`, `--force`:禁用提示,忽略不存在的文件

参考文档:

- [What is the difference between `rm -r` and `rm -f`?](https://superuser.com/questions/1126206/what-is-the-difference-between-rm-r-and-rm-f)

</details>

<details>
<summary><b><code>archive.tgz</code>有30GB大,如何列出其中内容并解压某个文件?</b></summary><br>

```bash
#列出文件
tar tf archive.tgz

#解压文件
tar xf archive.tgz filename
```

参考文档:

- [List the contents of a tar or tar.gz file](https://www.cyberciti.biz/faq/list-the-contents-of-a-tar-or-targz-file/)
- [How to extract specific file(s) from tar.gz](https://unix.stackexchange.com/questions/61461/how-to-extract-specific-files-from-tar-gz)

</details>

<details>
<summary><b>在一行中执行多个shell命令.</b></summary><br>

如果只想在前一个命令成功的情况下执行每个命令,那么使用`&&`运算符组合它们:

```bash
cd /my_folder && rm *.jar && svn co path to repo && mvn compile package install
```

如果其中一个命令失败了,则不会执行其后的所有命令.

如果要执行所有命令而不管先前的命令是否失败,请用分号分隔它们:

```bash
cd /my_folder; rm *.jar; svn co path to repo; mvn compile package install
```

还可以将所有命令放在脚本中并执行该命令:

```bash
#! /bin/sh
cd /my_folder \
&& rm *.jar \
&& svn co path to repo \
&& mvn compile package install
```

参考文档:

- [Execute combine multiple linux commands in one line (original)](https://stackoverflow.com/questions/13077241/execute-combine-multiple-linux-commands-in-one-line)

</details>

<details>
<summary><b><code>chmod</code>加什么参数可以让所有用户对某文件有执行权限且不影响其他权限?</b></summary><br>

```bash
chmod a+x /path/to/file
```

- `a` - 所有用户
- `x` - 执行权限
- `r` - 读权限
- `w` - 写权限

参考文档:

- [How to Set File Permissions Using chmod](https://www.washington.edu/computing/unix/permissions.html)
- [What does "chmod +x your_file_name" do and how do I use it?](https://askubuntu.com/questions/443789/what-does-chmod-x-filename-do-and-how-do-i-use-it)

</details>

<details>
<summary><b>如何同步2个本地目录?</b></summary><br>

在同一个系统上把**dir1**的内容同步到**dir2**中,输入:

```bash
rsync -av --progress --delete dir1/ dir2
```

- `-a, --archive` - 存档模式
- `--delete` - 删除目标目录中的无关文件
- `-v, --verbose` - 详细模式
- `--progress` - 传输时显示进度

参考文档:

- [How can I sync two local directories? (original](https://unix.stackexchange.com/questions/392536/how-can-i-sync-two-local-directories)
- [Synchronizing folders with rsync](https://www.jveweb.net/en/archives/2010/11/synchronizing-folders-with-rsync.html)

</details>

<details>
<summary><b>许多基本维护任务都需要编辑配置文件,介绍几种撤销修改的方法?</b></summary><br>

- 编辑前手动备份文件(比如:`cp filename{,.orig}`)
- 手动复制文件目录结构(比如:`cp`, `rsync` or `tar`)
- 在编辑器中备份源文件(比如:在编辑器配置文件中设定规则)
- 最好使用`git`或其他版本控制工具来保持追踪配置文件(比如:`etckeeper` 用于`/etc`目录)

参考文档:

- [Backup file with .bak before filename extension](https://unix.stackexchange.com/questions/66376/backup-file-with-bak-before-filename-extension)
- [Is it a good idea to use git for configuration file version controlling?](https://superuser.com/questions/1037211/is-it-a-good-idea-to-use-git-for-configuration-file-version-controlling)

</details>

<details>
<summary><b>如何查找所有大于20M的文件?</b></summary><br>

```bash
find / -type f -size +20M
```

参考文档:

- [How can I find files that are bigger/smaller than x bytes?](https://superuser.com/questions/204564/how-can-i-find-files-that-are-bigger-smaller-than-x-bytes)

</details>

<details>
<summary><b>为什么我们使用<code>sudo su -</code>而不是<code>sudo su</code>?</b></summary><br>

大多数现代Linux发行版都(不全是)禁用了root用户且没有设置密码,所以需要使用`sudo`.因此,使用`su`切换到root是不可行的(可以试下),只能使用`sudo su`来切换到root权限.

`su`只是切换用户,提供一个环境变量和之前的用户几乎一样的shell.

`su -`会在切换用户后再登陆shell,可以重置大多数环境变量,来提供一个干净的基础.

参考文档:

- [su vs sudo -s vs sudo -i vs sudo bash](https://unix.stackexchange.com/questions/35338/su-vs-sudo-s-vs-sudo-i-vs-sudo-bash)
- [Why do we use su - and not just su? (original)](https://unix.stackexchange.com/questions/7013/why-do-we-use-su-and-not-just-su)

</details>

<details>
<summary><b>如何查找系统中在过去60分钟修改过的文件?</b></summary><br>

```bash
find / -mmin -60 -type f
```

参考文档:

- [Get all files modified in last 30 days in a directory (orignal)](https://stackoverflow.com/questions/23070245/get-all-files-modified-in-last-30-days-in-a-directory)

</details>

<details>
<summary><b>保留旧日志的主要原因是?</b></summary><br>

它们在追查系统问题上是必不可少的,**日志管理**是IT安全的重要一部分.

服务器,防火墙和其他IT设备都会保留记录了重要的事件和事务信息的日志文件.这些信息可以提供从内部或外部发起的攻击网络的恶意活动的重要线索.日志也可以提供信息用来识别和解决设备问题,包括配置问题和硬件故障.

服务器可以记录了谁,什么时候访问了你的网站并浏览了什么信息,它非常详细,如下:

- 访问来自哪里
- 使用了什么浏览器来访问
- 具体查看了哪些文件
- 加载每个文件花了多长时间
- 以及其他一些专业信息

保留日志需要考虑的因素:

- 保留或销毁的法律依据
- 保丢或销毁的公司政策
- 日志的有效期
- 希望从日志中获取什么信息
- 日志占用了多大空间

通过收集和分析日志,可以了解到网络中发生了什么.如果知道如何阅读分析日志,那么每个日志文件中都包含了许多非常有用的信息.

参考文档:

- [How long do you keep log files?](https://serverfault.com/questions/135365/how-long-do-you-keep-log-files)

</details>

<details>
<summary><b>什么是增量备份?</b></summary><br>

增量备份是一种只复制自上次备份以来更新的文件的备份方式.

参考文档:

- [What Is Incremental Backup?](https://www.nakivo.com/blog/what-is-incremental-backup/)

</details>

<details>
<summary><b>什么是RAID?什么是RAID0,RAID1,RAID5,RAID6,RAID10?</b></summary><br>

<b>RAID</b> (Redundant Array of Inexpensive/Independent Disks)是一种提高数据存储性能和/或可靠性的技术.

- <b>RAID0</b>:也成为磁盘条带化,是一种将文件分割并将数据保存在RAID组中的所有磁盘驱动器的技术,没有任何冗余措施.

- <b>RAID1</b>:一种通过把数据写入2个磁盘来提高安全性的流行磁盘系统,也叫镜像化.RAID1不会提高写性能,但读性能约等于每个磁盘性能的和.当其中一个磁盘驱动器发生故障后,还可以使用另一个磁盘驱动,并在手动更换了故障的驱动器后,RAID控制器会把正常的工作驱动器上的全部内容复制到新的驱动器上.

- <b>RAID5</b>:一种通过计算奇偶校验数据来提高安全性,通过把数据分布在三个或更多驱动器的来提高速度(**条带化**)的磁盘系统.当单个驱动器发生故障时,可以读取计算分布式奇偶校验数据来恢复损坏盘中的数据.

- <b>RAID6</b>:RAID6通过新增一块奇偶校验盘来扩展RAID5.它至少需要4块磁盘,并能在2块盘同时发生故障时继续读写操作.RAID6对读操作没有性能损失,但由于计算奇偶校验的开销,在写操作上会有性能损失.

- <b>RAID10</b>:即RAID1+0,是一种结合了磁盘镜像化和磁盘条带化来保护数据的RAID配置.它至少需要4块盘,并把镜像的数据条带化.只要每对镜像化的磁盘中有一个正常工作,数据就可以恢复.但如果同一镜像对中的2块磁盘都发生了故障,那么由于条带化中没有奇偶校验,所有数据都会丢失.

参考文档:

- [RAID](https://www.prepressure.com/library/technology/raid)

</details>

<details>
<summary><b>如何指定和修改用户的默认组?</b></summary><br>

```bash
useradd -m -g initial_group username
```

`-g/--gid`:定义了用户初始登陆组的组名或组号.如果用这个参数指定了组名或组号,那组必须是已存在的.

如果没有使用该参数,那么将根据`/etc/login.defs`文件中的`USERGROUPS_ENAB`变量来决定useradd命令的结果.(`USERGROUPS_ENAB yes`)时默认创建一个与用户名相同的组,**GID**也等于**UID**.

参考文档:

- [How can I change a user's default group in Linux?](https://unix.stackexchange.com/questions/26675/how-can-i-change-a-users-default-group-in-linux)

</details>

<details>
<summary><b>日常工作和脚本编写的最佳命令行文本编辑器是什么? ***</b></summary><br>

待续.

</details>



<details>
<summary><b>为什么要把服务器放在机柜中?</b></summary><br>

- 保护硬件
- 方便降温
- 工作区组织化
- 更好地电源管理
- 更整洁的环境

参考文档:

- [5 Reasons to Rackmount Your PC](https://www.racksolutions.com/news/custom-projects/5-reasons-to-rackmount-pc/)

</details>

###### 网络问题 (23)

<details>
<summary><b>按如下情况画出网络拓扑图:20个系统,1个路由器,4个交换机,5台服务器和一个小型IP防火墙?***</b></summary><br>

待续.

</details>

<details>
<summary><b>如何理解OSI(或其他)模型?</b></summary><br>

- 我们可以将协议分配到不同层中
- 层提供了封装
- 层提供了抽象
- 层分隔开各功能

参考文档:

- [OSI Model and Networking Protocols Relationship](https://networkengineering.stackexchange.com/questions/6380/osi-model-and-networking-protocols-relationship)

</details>

<details>
<summary><b>VLAN和子网的区别是什么,需要用VLAN来设置子网吗?</b></summary><br>

**VLANs**和**子网**解决不同的问题.**VLANs**在第二层工作,用来隔离广播域.而**子网**在第三层工作,用来隔离IP地址.

**子网** - 是一组通过部分地址(通常称为网络地址)和子网掩码(网络掩码)确定的IP地址范围.例如,如果网络掩码是`255.255.255.0`(或简写为`/24`),并且网络地址是`192.168.10.0`,那么就定义了从`192.168.10.0`到`192.168.10.255`范围的IP地址,可以简写为`192.168.10.0/24`.

**VLAN** - 可以理解为"交换分区".假设有一台支持VLAN的8端口交换机,你可以将其中4个端口分配给一个**VLAN**(如`VLAN1`),另外4个端口分配给另一个**VLAN**(如`VLAN2`).`VLAN1`看不到`VLAN2`上的任何流量,反之亦然.从逻辑上来说,现在有2个独立的交换机.通常当交换机找不到MAC地址时,会把流量"泛洪"到所有端口,**VLANs**可以防止这个.

子网只是用来帮助主机在二层和三层上通信的一个定义IP地址范围的IP地址.每个子网不需要专属的**VLAN**.而**VLANs**是用来实现隔离的(相当于在二层通信的沙箱,2个不同**VLANs**的系统之间可以通过**VLAN间路由**来通信),为了方便管理和安全.

参考文档:

- [What is the difference between a VLAN and a subnet? (original)](https://superuser.com/questions/353664/what-is-the-difference-between-a-vlan-and-a-subnet)
- [VLANS vs. subnets for network security and segmentation](https://networkengineering.stackexchange.com/questions/46899/vlans-vs-subnets-for-network-security-and-segmentation)

</details>

<details>
<summary><b>列举5个你知道的常用网络端口?</b></summary><br>

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
    <td>20:传输数据;21:保持连接</td>
  </tr>
  <tr>
    <td>DNS</td>
    <td>53</td>
  </tr>
  <tr>
    <td>DHCP</td>
    <td>67/UDP:DHCP服务端;68/UDP:DHCP客户端</td>
  </tr>
  <tr>
    <td>SSH</td>
    <td>22</td>
  </tr>
</table>

参考文档:

- [Red Hat Enterprise Linux 4: Security Guide - Common Ports](https://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-sg-en-4/ch-ports.html)

</details>

<details>
<summary><b>什么是POP和IMAP?如何根据需求来选择?***</b></summary><br>

待续.

</details>

<details>
<summary><b>如何检查默认路由和路由表?</b></summary><br>
  
可以使用`netstat -nr`, `route -n`或`ip route show`命令来查看默认路由和路由表.

参考文档:

- [How to check routes (routing table) in linux](https://howto.lintel.in/how-to-check-routes-routing-table-in-linux/)
- [FreeBSD Set a Default Route/Gateway](https://www.cyberciti.biz/faq/freebsd-setup-default-routing-with-route-command/)

</details>

<details>
<summary><b>127.0.0.1和localhost之间的区别是什么?</b></summary><br>
  
嗯,最大的不同就是你还是不得不在某处查找localhost.

如果你使用`127.0.0.1`,那么软件会直接使用这个IP地址.`gethostbyname`(系统函数)的某些实现会检查dotted format(可能是等效的IPv6格式)而不再查找.

不然的话,必须解析主机名,并且不能保证你的hosts文件能解析正确,因为localhost可能改成一个完全不同的IP地址.

这意味着,在某些系统上,可以绕过本地的hosts文件.`host.conf`文件在Linux(和多数Unices)上可以控制这个.

如果你使用unix域套接字,速度会比TCP/IP稍快(系统开销小).Windows默认使用TCP/IP,而Linux根据你的选择来分,如果使用localhost,为unix域套接字,如果使用`127.0.0.1`,则是TCP/IP.

参考文档:

- [What is the difference between 127.0.0.1 and localhost?](https://stackoverflow.com/questions/7382602/what-is-the-difference-between-127-0-0-1-and-localhost)
- [localhost vs. 127.0.0.1](https://stackoverflow.com/questions/3715925/localhost-vs-127-0-0-1)

</details>

<details>
<summary><b><code>ping</code>命令使用了什么端口?</b></summary><br>

`ping`使用了**ICMP**协议,尤其是**ICMP echo request**和**ICMP echo reply**数据包,所以不存在所谓的端口.两个IP传输层协议,TCP和UDP,才用到端口.ICMP,TCP,UDP好比"兄弟姐妹",它们是独立的三个协议,运行在IP上.

**ICMP**数据包由IP数据报文头部的'协议'字段标识.**ICMP**不使用UDP或TCP通信服务,而是raw的IP通信服务.这表示IP数据报文的数据字段中直接携带了**ICMP**消息.`raw`表示在软件中实现创建和发送**ICMP**消息,打开`raw`套接字,构建包含**ICMP**消息的缓冲区,然后将包含信息的缓冲区写入`raw`套接字.

**ICMP**的IP协议值为1.协议字段是IP报文头的一部分,标识了该数据报文中的数据部分的内容.

使用 `nmap`可以查看端口是否打开:

```bash
nmap -p 80 example.com
```

参考文档:

- [Ping Port Number](https://networkengineering.stackexchange.com/questions/42463/ping-port-number)
- [Is it possible to ping an address:port?](https://superuser.com/questions/769541/is-it-possible-to-ping-an-addressport)

</details>

<details>
<summary><b>服务器A和服务器B之间通信失败,有哪些可能的原因?</b></summary><br>

解决服务器之间的通信问题,最好从TCP/IP栈来查:

1.**应用层**:两台服务器上的服务是否正常运行?是否配置正确(比如绑定的IP和端口正确吗)?应用和系统日志是否有明显报错?

2.**传输层**:应用使用的端口是否打开(试试telnet)?服务器是否能ping通?

3.**网络层**:系统或网络上的防火墙是否配置正确?IP堆栈是否配置正确(IP,路由,DNS等)?交换机和路由器是否正常工作(检查ARP表!)?

4.**物理层**:服务器联网了吗?是否有丢包的现象?

</details>

<details>
<summary><b>为什么你的服务器上解析不了主机?请修复这个问题. ***</b></summary><br>

待续.

</details>

<details>
<summary><b>如何用CLI来解析域名(使用外部DNS服务器)?IPs可以反解析到域名吗?</b></summary><br>

使用外部DNS服务器解析域名举例:

```bash
# with host command:
host domain.com 8.8.8.8

# with dig command:
dig @9.9.9.9 google.com

# with nslookup command:
nslookup domain.com 8.8.8.8
```

有时可以将IP地址解析回主机名.IP地址存储在**PTR**记录中,你可以这样:


```bash
dig A <hostname>
```

查找主机的IPv4地址.

```bash
dig AAAA <hostname>
```

查找主机的IPv6地址.

```bash
dig PTR ZZZ.YYY.XXX.WWW.in-addr.arpa.
```

查找IP地址`WWW.XXX.YYY.ZZZ`的主机名(注意八位字节是反转的), 或:

```bash
dig PTR b.a.9.8.7.6.5.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.8.b.d.0.1.0.0.2.ip6.arpa.
```

参考文档:

- [How can I resolve a hostname to an IP address in a Bash script?](https://unix.stackexchange.com/questions/20784/how-can-i-resolve-a-hostname-to-an-ip-address-in-a-bash-script)
- [How To Resolve IP Addresses To Domain Names?](https://superuser.com/questions/315687/how-to-resolve-ip-addresses-to-domain-names)

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
<summary><b>为什么要避免用<code>telnet</code>远程管理系统?</b></summary><br>

现在的操作系统默认关闭了所有有安全隐患的服务.另一方面,一些网路设备供应商仍然允许使用telnet协议建立通信.

**Telnet**使用了很不安全的连接来通信.它用纯文本格式在网络上发送数据,任何人都可以用网络工具轻松找到密码.

对**Telnet**来说,用纯文本格式来传递登陆凭证意味着在你的网路上运行嗅探器窃听**Telnet**登陆会话的任何人都能在几秒钟找到关键信息来控制你的设备.

参考文档:

- [Telnet and SSH as a secure alternative](https://www.ssh.com/ssh/telnet)
- [How to telnet to an IP address on a specific port?](https://superuser.com/questions/339107/how-to-telnet-to-an-ip-address-on-a-specific-port)

</details>

<details>
<summary><b><code>wget</code>和<code>curl</code>之间有什么不同?</b></summary><br>
  
主要区别:`wget`可以以递归方式下载而`curl`不可以.`wget`只支持命令行,`curl`支持FTP,FTPS,HTTP,HTTPS,SCP,SFTP,TFTP,TELNET,DICT,LDAP,LDAPS,FILE,POP3,IMAP,SMTP,RTMP和RTSP.

参考文档:

- [What is the difference between curl and wget? (original)](https://unix.stackexchange.com/questions/47434/what-is-the-difference-between-curl-and-wget)

</details>

<details>
<summary><b>什么是SSH以及它是如何工作的?</b></summary><br>

**SSH**代表**安全的Shell**.它是一种协议,允许你从通过服务器A跳转到服务器B的shell会话,然后和服务器B进行交互.

要建立一个**SSH**连接,需要远程服务器(B)运行**SSH**服务端进程并且用户的计算机(A)运行**SSH**客户端.

**SSH**服务端和客户端都监听一个特定的网络端口(默认是22),并对连接请求进行身份验证,当用户提供了正确的凭据时生成相应的工作环境.

参考文档:

- [Understanding the SSH Encryption and Connection Process](https://www.digitalocean.com/community/tutorials/understanding-the-ssh-encryption-and-connection-process)
  
</details>

<details>
<summary><b>为什么多数教程建议使用更安全的SSH密钥认证而不是密码认证?</b></summary><br>

**SSH密钥**是SSH协议中的访问凭证.它的功能类似用户名和密码,但密钥主要用于自动化流程和为系统管理员或高级用户实现单点登录.

SSH通过公钥和私钥的非对称加密算法来确认客户端的身份而不是用户密码.

如果你的SSH服务仅允许公钥认证,那么攻击者需要一份与存储在服务器上的公钥相对应的私钥副本才能成功.

如果你的SSH服务允许密码认证,那么在公网上的SSH服务器将每时每刻被僵尸网络攻击,试图猜测用户名和密码.僵尸网络不需要任何信息,只需尝试流行的用户名和密码组合.这将会堵塞日志.

参考文档:

- [Key-Based Authentication (Public Key Authentication)](http://www.crypto-it.net/eng/tools/key-based-authentication.html)
- [SSH password vs. key authentication](https://security.stackexchange.com/questions/33381/ssh-password-vs-key-authentication)

</details>

<details>
<summary><b>什么是包过滤器以及它是如何工作的?</b></summary><br>  
  
**包过滤器**是一种防火墙技术,它控制网络访问的方式是:监控传入和传出的包并根据包中的源地址,目的地址,协议,端口等决定是否让包传递到系统网络或直接丢弃.

包过滤适用于比较简单的安全要求,很多组织的内部(私人)网络没有分的很细,不需要高度复杂的防火墙来隔离.包过滤设备是一种隔离子网的合适方式.

它在网络层和传输层的TCP/IP协议栈中进行操作,检查每个进入协议栈的数据包,并仔细检查数据包的头部来获取以下信息:

- **协议(IP报头,网络层)** - 在IP报头中,前9个字节(从零开始计数)标识了数据包的协议.大多数过滤设备都能够区分TCP,UPD和ICMP.

- **源地址(IP报头,网络层)** - 源地址是创建该数据包的主机的32位IP地址.

- **目标地址(IP报头,网络层)** - 目标地址是该数据包要发送的目标主机的32位IP地址.

- **源端口(TCP或UDP报头,传输层)** - 每个TCP或UDP的网络连接端都绑定了一个端口.TCP端口是独立的,和UDP端口不同.端口数小于1024的是有明确用途的保留端口,端口数大于等于1024的是临时端口,由软件自己选择.关于"默认端口"列表,请参阅RFP1700.源端口是随机分配的临时端口,所以对源端口进行过滤不是很有用.

- **目标端口(TCP或UDP报头,传输层)** -目标端口号表示数据包要发送到的端口.目标主机上每个服务都监听了一个端口.一些默认的可能会被过滤的端口为20/TCP和21/TCP(ftp连接和数据),23/TCP(telnet),80/TCP(http),53/TCP(DNS).

- **连接状态(TCP报头,传输层)** - 连接状态会标识该数据包是否是网络会话的第一个数据包.如果这是会话中的第一个数据包,则TCP标头中的ACK位设置为"false"或0.可以通过拒绝或丢弃任何ACK位设置为"false"或0的数据包来禁止主机建立连接.

参考文档:

- [Building Internet Firewalls - Packet Filtering](http://web.deu.edu.tr/doc/oreily/networking/firewall/ch06_01.htm)
 
</details>

<details>
<summary><b>使用反向代理服务器的优点是什么?</b></summary><br>    
  
**隐藏后端服务器的拓扑和特性**

**反向代理服务器**可以隐藏源服务器的存在和特性,用来充当互联网和web服务器之间的中介.特别是使用web托管服务器时,安全性更高.

**让后端服务器维护更透明**

所有运行在反向代理后的服务器上的更改对最终用户都是完全透明的.

**负载均衡**

反向代理服务器会强制使用以下负载均衡算法来分配集群中的服务器负载:循环,加权循环,最少连接,加权最少连接或随机.

当某台服务器出现故障时,系统会将流量自动调度到正常的服务器来让用户继续进行安全的文件传输活动.

**SSL处理**

处理收到的HTTPS连接,解密请求并将解密后的请求转发到web服务器.

**URL转发**

可以使用单个ip但是不同的URL来路由到不同的后端服务器.

参考文档:

- [The Benefits of a Reverse Proxy](https://dzone.com/articles/benefits-reverse-proxy)

</details>

<details>
<summary><b>路由和网关之间的区别是什么?什么是默认路由?</b></summary><br>      
  
**路由**是一种三层转发的技术功能或实现这个功能的硬件设备,而网关是提供本地网段间连接通信的功能.可以"将路由器设置为网关".另一个术语是hop,用于子网间的转发.

**默认网关**指的是你的LAN上的负责联络外部LAN流量的第一个连接点的路由地址.

只是功能不同,设备是一样的.

参考文档:

- [Difference between router and gateway (orignal)](https://networkengineering.stackexchange.com/questions/51426/difference-between-router-and-gateway)

</details>

<details>
<summary><b>解释以下DNS的每个记录的功能:SOA, PTR, A, MX, 以及CNAME?</b></summary><br>      
  
DNS记录实质上是映射的文件,用来告诉DNS服务器每个域名和其对应的IP地址,以及如何处理发送给每个域名的请求.绝大部分DNS的记录配置使用以下记录类型:`A`, `AAAA`, `CNAME`, `MX`, `PTR`, `NS`, `SOA`, `SRV`, `TXT`, 和`NAPTR`.

- **SOA** - 起始授权机构记录
- **A** - 域名指向ip地址记录
- **AAAA** - 域名指向ipv6地址记录
- **CNAME** - 域名指向另一个域名记录
- **MX** - 域名指向邮件服务器地址记录
- **NS** - 域名服务器记录
- **PTR** - 反向解析记录

参考文档:

- [List of DNS record types](https://en.wikipedia.org/wiki/List_of_DNS_record_types)

</details>

<details>
<summary><b>为什么MAC地址替代不了IPv4/6在网络中的作用?</b></summary><br>

现代网络被分为很多不同的层来完成端到端的通信.网卡(mac地址,物理地址)只需要负责与其物理网络的对端通信即可.

使用**MAC**完成的通信被局限于有直接物理连接的设备.比如,在互联网中,你的电脑并没有物理连接到每台设备,所以我们要使用**TCP/IP**(**3层**,逻辑地址)机制来实现通信.

**IP**是一组计算机上的有层次的随机数字格式,以逻辑来区分这些计算机是否是一个组(即子网).在这些组之间通过路由表来发送信息,路由表分为多个级别,因此我们不需要追踪每个子网.

另一方面,整个网络中的**MAC**地址都是随机分配的,与拓扑完全无关.路由分组是不可行的,每个路由器都需要跟踪每个通过它传输流量的设备的路线.这就是**2层**交换机的工作,而且有一定数量限制.

参考文档:

- [Why couldn't MAC addresses be used instead of IPv4|6 for networking? (original)](https://serverfault.com/questions/410626/why-couldnt-mac-addresses-be-used-instead-of-ipv46-for-networking)

</details>

<details>
<summary><b>可以用于最多30台设备的最小IPv4子网掩码是什么?</b></summary><br>      

最大30台设备的话是`/27`,或子网掩码`255.255.255.224`.

参考文档:

- [How do you calculate the prefix, network, subnet, and host numbers?](https://networkengineering.stackexchange.com/questions/7106/how-do-you-calculate-the-prefix-network-subnet-and-host-numbers)
- [The slash after an IP Address - CIDR Notation](https://networkengineering.stackexchange.com/questions/3697/the-slash-after-an-ip-address-cidr-notation)
- [Why are there 3 ranges of private IPv4 addresses?](https://networkengineering.stackexchange.com/questions/32119/why-are-there-3-ranges-of-private-ipv4-addresses)
- [IP Calculator](http://jodies.de/ipcalc)

</details>

<details>
<summary><b>讲下常用的HTTP状态码?</b></summary><br>      

- **1xx** - 信息响应 - 传递传输协议级别的信息
- **2xx** - 成功 - 表示客户端的请求已成功接受
- **3xx** - 重定向 - 表示客户端需要一些其他操作才能完成其请求
- **4xx** - 客户端错误 - 这类错误码表示客户端有问题
- **5xx** - 服务端错误 - 这类错误码表示服务端有问题

参考文档:

- [HTTP Status Codes](https://httpstatuses.com/)

</details>

###### Devops问题 (5)

<details>
<summary><b>什么是DevOps?对一个DevOps社区来说哪个更重要:人们如何沟通或选择部署的工具? ***</b></summary><br>

**DevOps**是一个同时从事开发和运维任务的有凝聚力的团队,或者是密切合作的个别运维和开发团队.它更像是与其他部门合作实现共同目标的一种"方式".

</details>

<details>
<summary><b>什么是版本控制?提交信息如何写得优雅?</b></summary><br>      

版本控制是一个根据时间来记录文件或文件夹变化的系统,它可以让你在以后回调特定的文件版本.版本控制系统包括一个集中共享仓库,用来记录协作者提交的对文件或文件夹的更改.以下为版本控制的作用.

版本控制可以让你:

- 将文件恢复为之前的状态
- 将整个项目恢复为之前的状态
- 根据时间来比较更改内容
- 查找可能导致问题的最后的修改是谁写的
- 谁,什么时候提出了什么问题

写好提交信息的七条建议:

- 用空行将主题和正文分开
- 限制主题行为50字符
- 主题行要用大写字母开头
- 不要用句号结束主题行
- 主题行要用虚拟语气
- 正文要在72个字符处换行
- 正文要解释what和why而不是how

参考文档:

- [Getting Started - About Version Control (original)](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)

</details>

<details>
<summary><b>简述一些<code>git</code>基本命令.</b></summary><br>      

- `git init` - 创建一个新的本地仓库
- `git commit -m "message"` - 提交更改
- `git status` - 显示工作目录和暂存区的状态
- `git push origin master` - 把更改推送到远程仓库项目的master分支

</details>

<details>
<summary><b>简述一个简单的持续集成流水线.</b></summary><br> 

- 克隆源代码
- 发布到QA环境
- 测试QA环境
- 发布到生产环境

</details>

<details>
<summary><b>简述<code>docker</code>基础命令.</b></summary><br>

- `docker ps` - 显示正在运行的容器
- `docker ps -a` - 显示所有的容器
- `docker images` - 显示docker的镜像
- `docker logs <container-id|container-name>` - 显示容器的日志
- `docker network ls` - 显示所有docker虚拟网络
- `docker volumes ls` - 显示所有docker的挂载目录
- `docker exec -it <container-id|container-name> bash` - 使用交互式shell在容器中执行bash

</details>

###### 网络安全问题 (1)

<details>
<summary><b>什么是错误的安全配置?</b></summary><br>

当设备/程序/网络的配置方式可以被攻击者利用时,就是一种**错误的安全配置**.简单例子:使用默认的用户名/密码,简单的设备账户名等.

</details>

### :diamond_shape_with_a_dot_inside: 中级系统管理员

###### 系统问题 (50)

<details>
<summary><b>谈谈你对生产环境的经验? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>你会选择哪个发行版来作为主要的web服务器? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>通过以下几点简述Linux启动流程.</b></summary><br>
  
**BIOS**:BIOS的全称为Basic Input or Output System,它先执行系统完整性检查,然后在MBR中查找并执行bootloader.

**Bootloader**:早期的操作系统,x86和x86-64架构被设计成当主引导记录(MBR)内的代码被执行了并加载了第一阶段的bootloader后启动基于BIOS的引导加载程序.在UEFI系统中,可以直接执行类似Linux内核的payload,因此不需要引导加载程序.常见的Bootloader有:**GRUB**,**Syslinux/Isolinux**或**Lilo**.

**MBR**:MBR全称为Master Boot Record,MBR记录了有关GRUB的信息,并执行和加载该GRUB.

**GRUB**:GRUB全称为Grand Unified Bootloader.如果系统上安装了多个内核镜像,那么需要选择加载哪个内核.

**Kernel**:Linux中的内核处理所有操作系统进程,比如内存管理,任务调度,I/O,进程间通信,和系统整体控制.内核(压缩镜像文件)被加载到内存中并解压缩,并设置一些基本功能,比如基本内存管理功能.

**Init**:它是系统上所有进程的父进程,有内核执行,用来启动其他进程.

- `SysV init` - init的工作是"在内核完全启动时让所有程序按要求运行".根据设定的默认运行级别,系统执行对应的程序.实际上是它建立并操作了整个用户空间,包括检查和挂载文件系统,启动必要的用户服务,并在系统启动完成后切换到用户环境.

- `systemd` - systemd被开发用于取代目前从Unix中继承的System V这个Linux init系统.
类似init,systemd也是一个管理其他守护进程的守护进程.所有守护进程(包括systemd)都是后台进程.Systemd是第一个启动(开机时)和最后一个停止(关机时)的守护进程.

- `runinit` - runinit是类Unix操作系统的初始化进程,用于初始化,监控和停止所有操作系统上的进程.它是在Linux,Mac OS X,\*BSD,和Solaris操作系统上运行的进程监控组件的重写.

**Runlevel programs**:根据设定的默认运行级别,系统执行对应的程序.

参考文档:

- [Analyzing the Linux boot process](https://opensource.com/article/18/1/analyzing-linux-boot-process)
- [Systemd Boot Process a Close Look in Linux](https://linoxide.com/linux-how-to/systemd-boot-process/)

</details>
  
<details>
<summary><b>为什么单核服务器上负载为1.00时不太好?</b></summary><br>
  
负载为1.00时表示cpu没有空闲.实际操作中,很多系统管理员会设定一个值:0.70.

当服务器的平均负载保持在0.70以上时,那么在事情变得更糟前就需要检查了.

当服务器的平均负载保持在1.00以上时,需要马上找出问题并修复,不然就要在半夜起来啦,这并不有趣.

当服务器的平均负载保持在5.00以上时,可能会遇到严重的问题,建议将服务器挂起,不然就会(莫名其妙)地在一些糟糕的时间发生问题,比如半夜或开会时.不要出现这种情况.

参考文档:

- [Proper way of interpreting system load on a 4 core 8 thread processor](https://serverfault.com/questions/618130/proper-way-of-interpreting-system-load-on-a-4-core-8-thread-processor)
- [Understanding Linux CPU Load - when should you be worried?](http://blog.scoutapp.com/articles/2009/07/31/understanding-load-averages)

</details> 

<details>
<summary><b>当生效用户是root,但实际用户ID是你的名字时意味着什么?</b></summary><br>

**实际用户ID**是你启动进程的用户,**有效用户ID**是由操作系统来决定你是否被允许执行某些操作(大多数情况下,偶有例外).

当你登陆后,shell通过password文件同时把**实际用户ID**和**有效用户ID**设定为同一值.

比如,你执行了setuid(一个函数),并且没有用其他(例如**root**)用户运行,那么setuid程序做了以下操作:

setuid会获取你的**实际ID**(基于你是程序属主)和文件属主的**有效用户ID**(例如**root**).

当`passwd`的权限如下:

```bash
-rwsr-xr-x 1 root root 45396 may 25  2012 /usr/bin/passwd
```

当user2想修改密码时,执行`/usr/bin/passwd`.

**RUID**会变为user2但是程序的**EUID**会变为root.

user2用passwd只能来修改它自己的密码,因为passwd会检查**RUID**是不是user2.如果**RUID**不是root的话,passwd被限制只能修改实际用户的密码.

因为passwd命令需要把结果写入`/etc/passwd` 和/或 `/etc/shadow`,所以执行passwd时**EUID**是root是必须的.

参考文档:

- [Difference between Real User ID, Effective User ID and Saved User ID? (original)](https://stackoverflow.com/questions/30493424/what-is-the-difference-between-a-process-pid-ppid-uid-euid-gid-and-egid)
- [What is the difference between a pid, ppid, uid, euid, gid and egid?](https://stackoverflow.com/questions/30493424/what-is-the-difference-between-a-process-pid-ppid-uid-euid-gid-and-egid)

</details>

<details>
<summary><b>开发人员添加了生成大量日志文件的定时任务,如何避免单个文件变的过大?</b></summary><br>

处理日志文件可以使用`logrotate`.不过应该在将任务添加在`/etc/logrotate.d/`中而不是直接在 `/etc/logrotate.conf`中修改.不然当有版本升级时就会有很多配置文件差异了.

如果文件写入比较频繁,可以使用截断功能:

```bash
: >/var/log/massive-logfile
```

这可以在不中断进程的情况下截断文件,非常方便.

参考文档:

- [How to Use logrotate to Manage Log Files](https://www.linode.com/docs/uptime/logs/use-logrotate-to-manage-log-files/)
- [System logging](https://www.ibm.com/developerworks/library/l-lpic1-108-2/index.html)

</details>

<details>
<summary><b>Linux内核如何创建,管理和删除系统中的进程? ***</b></summary><br>

待续

参考文档:

- [Linux Processes](https://www.tldp.org/LDP/tlk/kernel/processes.html)

</details>

<details>
<summary><b>简介在<code>top</code>和<code>htop</code>看到的信息.如何使用这些工具来诊断负载,高cpu占用和内存不足等问题? ***</b></summary><br>

待续.

参考文档:

- [top explained visually](https://www.svennd.be/top-explained-visually/)
- [htop Explained Visually](https://codeahoy.com/2017/01/20/hhtop-explained-visually/)
- [Explanation of everything you can see in htop/top on Linux](https://peteris.rocks/blog/htop/)

</details>

<details>

<summary><b>如何识别进程占用的资源?</b></summary><br>

可以使用`top`来查看:
- **M** 根据当前的常驻内存大小排序
- **T** 根据总计(或累计)的CPU使用量排序
- **P** 根据当前CPU的使用量排序(默认刷新)
- **?** 显示所有top的命令使用帮助

当服务器运行缓慢,需要决定杀死哪些进程或卸载哪些软件时,就可以通过这个来获取需要的信息.

参考文档:

- [How to find the process(es) which are hogging the machine](https://superuser.com/questions/326300/how-to-find-the-processes-which-are-hogging-the-machine)

</details>

<details>
<summary><b>在200台服务器上升级<code>ntpd</code>服务到最新版本的最佳方式是什么?</b></summary><br>

通过使用**Infrastructure as a Code**(代码即设施),有以下几种方法:

1. **配置同步变更管理模型**:

很多配置管理工具(Ansible, Chef, Puppet, Saltstack, ...)可以在所有服务器上自动更新`ntpd`服务.为了系统稳定性,一般只自动更新安全相关的包.为了防止错误配置,软件包的主版本号和次版本号在配置管理中都是被固定的.可以通过修改配置管理中的`ntpd`的版本号来更新部署.

使用这种方式将更新部署到基础服务器设施时要格外小心.实施部署前需要经过单元,集成和系统测试,并先部署到演示环境来保证配置无误.如果测试证明配置正确,则开始增量部署,以便出现错误或故障时进行回滚.

2. **不可变服务模型**:

在不可变服务模型中,整个单元(服务器,容器)都会被要更新的镜像替代而不是更改正在运行的服务器(这可以排除配置差异).这种方式需要用Packer或Docker和Dockerfile等工具来构建服务镜像,然后像上述(1.)中测试和部署该镜像,不过目前可以使用Canary Release等技术来实现增量转出和回滚的功能.

参考文档:

- [Infrastructure as a Code - Chapter 8: Patterns for Updating and Changing Servers](http://shop.oreilly.com/product/0636920039297.do)

</details>

<details>
<summary><b>当服务器启动时在console中报错了,该如何找到这些信息并检查?</b></summary><br>

console中有2种类型的信息:

- **由内核生成** (通过printk)
- **由用户空间生成** (通常是操作系统)

内核信息总是存储在**kmsg**缓冲区中,可以通过`dmesg`命令查看,也常被复制到**syslog**中.用户空间信息也会被写入`/dev/kmsg`中,不过非常少见.

与此同时,当用户空间将它花哨的启动状态信息写入`/dev/console`或`/dev/tty1`中时,它仅仅是显示在屏幕上而不存储在任何地方.

`dmesg`可以用来回顾系统启动时的信息.这个命令可以显示在内核ring buffer中的系统信息.启动完成后我们可以马上执行该命令来查看启动信息.ring buffer是一种固定大小的缓冲区,任何添加到其中的新数据都会覆盖之前的旧数据.

引导过程完成后会显示后续操作,比如传递命令行选项给内核,检测到有新的USB硬件设备添加,或由于NIC(网络适配器)问题而无法连接到网络的错误等.

如果系统已经是登录状态则应该使用`journalctl`命令来查看日志,它包括了内核和启动时的信息,以及syslog和各种系统服务的信息.

启动时的问题或报错要求管理员根据不同的Linux版本使用特定的命令来查看如下重要文件:

- `/var/log/boot.log` - 系统启动日志,包括系统启动时的所有内容.
- `/var/log/messages` - 存储全局系统信息,包括系统启动时的信息.
- `/var/log/dmesg` - 包括内核ring缓冲区中的信息.

参考文档:

- [How to view all boot messages in Linux after booting? (original)](https://superuser.com/questions/1188407/how-to-view-all-boot-messages-in-linux-after-booting)
- [Differences in /var/log/{syslog,dmesg,messages} log files](https://superuser.com/questions/565927/differences-in-var-log-syslog-dmesg-messages-log-files)
- [How can the messages that scroll by when booting a Debian system be reviewed later?](https://serverfault.com/questions/516411/all-debian-boot-messages)

</details>

<details>
<summary><b>Swap使用率过高,可能的原因以及如何解决?</b></summary><br>

**Swap**空间是一种定量的物理内存,当可用内存不足时操作系统会使用这部分内存.它的内存管理涉及交换部分内存到物理存储和从物理存储交换到内存.

如果系统需要更多内存资源而RAM用完了,那么内存中的非活动页面将移到交换空间中.虽然交换空间可以帮到一些内存小的机器,但它不能被当作RAM的替代品,因为**Swap**空间位于硬盘上,访问速度比物理内存慢很多.

RAM需求会随着工作量而增加,如果整个swap量都用完了则表明需要更多的内存.此外,将`swappiness`(/proc/sys/vm/swappiness)改为**1**可能不是一个明智的决定.当`swappiness`为**1**时并不代表着不会交换,而是表示内核在交换方面的积极程度,当系统有需求时还是会进行交换的.

- **增加交换空间大小** - 首先,需要增加磁盘用量,如果磁盘速度不是足够快,那么系统可能会卡顿崩溃,并会在数据进出内存时有速度下降的问题,这些都会导致瓶颈.

- **增加RAM** - 真正的解决方案是增加更多内存.RAM没有替代品,只要有足够多的内存,那么交换内存用到的就会少.

监控交接空间使用情况:

- `cat /proc/swaps` - 查看全部的和已使用的交换空间
- `grep SwapTotal /proc/meminfo` - to 查看全部的交换空间
- `free` - 显示已用的和空闲的系统内存(包括swap)
- `vmstat` - 显示交换空间的统计信息
- `top`, `htop`- 显示swap的使用情况
- `atop` - 显示系统过度使用的内存
- 或使用一行shell命令来列出所有应用程序的swap使用量(以kilobytes为单位):
```bash
for _fd in /proc/*/status ; do
  awk '/VmSwap|Name/{printf $2 " " $3}END{ print ""}' $_fd
done | sort -k 2 -n -r | less
```

参考文档:

- [Linux ate my ram!](https://www.linuxatemyram.com/)
- [How to find out which processes are using swap space in Linux?](https://stackoverflow.com/questions/479953/how-to-find-out-which-processes-are-using-swap-space-in-linux)
- [8 Useful Commands to Monitor Swap Space Usage in Linux](https://www.tecmint.com/commands-to-monitor-swap-space-usage-in-linux/)
- [What is the danger in having a fully used SWAP in an Ubuntu server?](https://serverfault.com/questions/499301/what-is-the-danger-in-having-a-fully-used-swap-in-an-ubuntu-server)
- [How to empty swap if there is free RAM?](https://askubuntu.com/questions/1357/how-to-empty-swap-if-there-is-free-ram)

</details>

<details>
<summary><b>什么是umask?如何为某用户永久设置?</b></summary><br>

在Linux和类Unix操作系统上,创建新文件时会使用一组默认权限.具体来说,新文件的权限由称为umask的的权限"掩码"来决定.umask命令可以用来设置或显示这个掩码值.

永久设置 (在下列文件中设置比如`umask 02`):

- `~/.profile`
- `~/.bashrc`
- `~/.zshrc`
- `~/.cshrc`

参考文档:


- [What is Umask and How To Setup Default umask Under Linux?](https://www.cyberciti.biz/tips/understanding-linux-unix-umask-value-usage.html)

</details>

<details>
<summary><b>简述下列umask的不同之处: 000, 002, 022, 027, 077 和 277.</b></summary><br>

<table style="width:100%">
  <tr>
    <th>Umask</th>
    <th>文件权限</th>
    <th>目录权限</th>
  </tr>
  <tr>
    <td>000</td>
    <td>666 rw- rw- rw-</td>
    <td>777 rwx rwx rwx</td>
  </tr>
 <tr>
    <td>002</td>
    <td>664 rw- rw- r--</td>
    <td>775 rwx rwx r-x</td>
  </tr>
  <tr>
    <td>022</td>
    <td>644 rw- r-- r--</td>
    <td>755 rwx r-x r-x</td>
  </tr>
<tr>
    <td>027</td>
    <td>640 rw- r-- ---</td>
    <td>750 rwx r-x ---</td>
  </tr>
<tr>
    <td>077</td>
    <td>600 rw---- ---</td>
    <td>700 rwx --- ---</td>
  </tr>
<tr>
    <td>277</td>
    <td>400 r-- --- ---</td>
    <td>500 r-x --- ---</td>
  </tr>
</table>

参考文档:

- [What is Umask and How To Setup Default umask Under Linux?](https://www.cyberciti.biz/tips/understanding-linux-unix-umask-value-usage.html)

</details>

<details>
<summary><b>符号链接和硬链接之间的区别?</b></summary><br>

文件系统中的文件都由inodes来标识(单个或多个).

- 文件系统中的文件基本都是一个指向inode的链接
- 硬链接创建一个新的文件,包括了指向同一个inode的链接

删除文件时,只是删除了一个指向inode的链接,只有删除了所有指向inode的链接才会删除(或删除或可写入)该inode.

- 符号链接是文件系统中名字不同的一个链接.

一旦硬链接建立,链接就指向inode了,删除,重命名或移动源文件都不会影响硬链接,因为它链接的是底层的inode.对inode中的数据的改动会影响到所有引用该inode的文件.

注意:硬链接只在同一文件系统中有效.符号链接可以跨文件系统,因为它们只是另一个名称的文件.

不同之处:

- **硬链接**不能用于目录,只能用于单个文件
- **软链接**也称为符号链接,可以用于链接目录

参考文档:

- [What is the difference between a hard link and a symbolic link?](https://medium.com/@wendymayorgasegura/what-is-the-difference-between-a-hard-link-and-a-symbolic-link-8c0493041b62)

</details>

<details>
<summary><b>粘滞位如何工作的?和<code>SUID/GUID</code>一样吗?</b></summary><br>

这可能是最烦人的事之一,但**粘滞位**和**SUID/GUID**位是完全不同的东西.

使用`man chmod`命令可以查看**SUID**和**粘滞位**的介绍.

**SUID/GUID**

rwxrwxrwx中的用户权限位(第一组rwx)和组权限位(第二组rwx)中的x可以替换为s来新增额外的状态.当x为s时,该文件(假设是程序而非脚本)的实际执行权限为文件的属主或属组.

所以,当文件属主为root且**SUID**位已打开,那么及时用普通用户执行,实际运行用户还是root.同样适用于**GUID**位.

例如:

**无suid/guid** - 设置为`rwxr-xr-x`.

```bash
ls -lt b.pl
-rwxr-xr-x 1 root root 179 Jan  9 01:01 b.pl
```

**启用suid和用户执行权限(小写s)** - 设置为`rwsr-x-r-x`.

```bash
chmod u+s b.pl
ls -lt b.pl
-rwsr-xr-x 1 root root 179 Jan  9 01:01 b.pl
```

**启用suid并禁用用户执行权限(大写S)** - 设置为`rwSr-xr-x`.

```bash
chmod u-x b.pl
ls -lt b.pl
-rwSr-xr-x 1 root root 179 Jan  9 01:01 b.pl
```

**启用guid和组执行权限(小写s)** - 设置为`rwxr-sr-x`.

```bash
chmod g+s b.pl
ls -lt b.pl
-rwxr-sr-x 1 root root 179 Jan  9 01:01 b.pl
```

**启用guid并禁用组执行权限(大写S)** - 设置为`rwxr-Sr-x`.

```bash
chmod g-x b.pl
ls -lt b.pl
-rwxr-Sr-x 1 root root 179 Jan  9 01:01 b.pl
```

**粘滞位**

粘滞位适用`t`来显示,比如`/tmp`目录:

```bash
ls -l /|grep tmp
drwxrwxrwt. 168 root root 28672 Jun 14 08:36 tmp
```

这个根据实际作用应该称为"限制删除位".当启用该模式时,它会使该目录中的文件和目录只能由其所属的用户和组删除.

参考文档:

- [How does the sticky bit work? (original)](https://unix.stackexchange.com/questions/79395/how-does-the-sticky-bit-work)

</details>

<details>
<summary><b>在命令执行前<code>LC_ALL=C</code>做了什么?什么情况下它会有用?</b></summary><br>

`LC_ALL`是一个会覆盖所有本地化设置的环境变量,它会一次将所有`LC_`类型的变量设定为指定的语言环境.

在命令执行前设置`LC_ALL=C`的主要原因是为了得到英语输出(通常更改使用命令时的语言环境).

另一方面,当执行如`grep`或`fgrep`命令时用`LC_ALL=C`可以提高命令执行速度.`LC_ALL=C`语言环境提高了命令执行性能并降低了执行时间.

比如,如果设置了`LC_ALL=en_US.utf8`,那么系统会从`/usr/lib/locale`目录中打开多个文件,而`LC_ALL=C`的话是打开和读取最少的文件.

如果需要重置当前会话的所有常规(初始)语言环境设置:

```bash
LC_ALL=
```

如果`LC_ALL`没起作用,试试`LANG`(如果还是没起作用,再试试`LANGUAGE`):

```bash
LANG=C date +%A
Monday
```

参考文档:

- [What does LC_ALL=C do? (original)](https://unix.stackexchange.com/questions/87745/what-does-lc-all-c-do)
- [Speed up grep searches with LC_ALL=C](https://www.inmotionhosting.com/support/website/ssh/speed-up-grep-searches-with-lc-all)

</details>

<details>
<summary><b>配置服务器时有个步骤是设置apps的目录权限,请问该怎么做以及有哪些错误需要避免?</b></summary><br>

**1) 主要要求 - 牢记这一点**

- 哪些用户有权限访问该app文件系统
- web服务器(Apache)和app服务器(uwsgi)的权限
- 特殊目录(**uploads**,**cache**)和ap主要目录(`/var/www/app01/html`)的权限
- 正确的`umask`值和**suid**/**sgid**(特殊情况)
- 所有后续文件和目录的权限
- 定时任务和脚本的权限

**2) 应用程序目录**

`/var/www`目录包括了每个网站,比如:`/var/www/app01`,`/var/www/app02`

```bash
mkdir /var/www/{app01,app02}
```

**3) 应用程序属主和属组**

每个应用程序都有一个设定好的**属主**(如:**u01-prod**,**u02-prod**)何**属组**(如:**g01-prod**,**g02-prod**),用来当网站目录中所有文件和目录的所有者:

```bash
chown -R u01-prod:g01-prod /var/www/app01
chown -R u02-prod:g02-prod /var/www/app02
```

**4) 开发者属主和属组**

所有维护网站的用户都有自己的组,将它们附加到应用程序的组:

```bash
id alice
uid=2000(alice) gid=4000(alice) groups=8000(g01-prod)
id bob
uid=2001(bob) gid=4001(bob) groups=8000(g01-prod),8001(g02-prod)
```

如上所示,**alice**用户有`/var/www/app01`的标准权限,**bob**用户拥有`/var/www/app01`和 `/var/www/app02`的标准权限.

**5) Web服务器属主和属组**

任何需要由web服务器生成的文件或目录都有其自己的属主.如Apache服务器,默认属主/属组是**apache:apache**或**www-data:www-data**,而Nginx是**nginx:nginx**.建议不要修改这些设置.

如果应用程序运行于app服务器上,如**uwsgi**或**php-fpm**,那么需要在特定的配置文件中设置合适的用户和组(如:**app01**服务器的用户和组是**u01-prod:g01-prod**).

**6) 权限**

使用**访问控制列表**设置合适的权限:

```bash
# For web server
setfacl -Rdm "g:apache:rwx" /var/www/app01
setfacl -Rm "g:apache:rwx" /var/www/app01

# For developers
setfacl -Rdm "g:g01-prod:rwx" /var/www/app01
setfacl -Rm "g:g01-prod:rwx" /var/www/app01
```

如果使用**SELinux**需要设置下面配置:

```bash
chcon -R system_u:object_r:httpd_sys_content_t /var/www/app01
```

**7) 安全错误**

- 文件和目录使用了**root**权限
- 永远不在网站目录中使用**root**执行或创建任何文件
- 使用了像**777**这样的权限导致让一些关键文件变得全世界都可以读写
- 避免维护脚本和关键文件的suid位使用root

如果允许站点修改构成网站的代码文件,那很容易让人接管你的服务器.

文件上传工具允许用户上传任意名称和内容的文件.这会导致有人上传一个PHP邮件转发脚本到你的网站,并将你的服务器变为转发垃圾邮件的肉鸡,还可能读取数据库中的所有信息.

如果恶意用户可以上传任意名称和内容的文件,那么他们能轻易上传并覆盖index.php(或其他重要文件)来破坏你的网站.

参考文档:

- [How to setup linux permissions for the WWW folder?](https://serverfault.com/questions/124800/how-to-setup-linux-permissions-for-the-www-folder)
- [What permissions should my website files/folders have on a Linux webserver?](https://serverfault.com/questions/357108/what-permissions-should-my-website-files-folders-have-on-a-linux-webserver)
- [Security Pitfalls of setgid Programs](https://www.agwa.name/blog/post/security_pitfalls_of_setgid_programs)

</details>

<details>
<summary><b>在运行级别3运行<code>telinit 1</code>时,init做了哪些操作?最终会造成什么结果?如果使用<code>telinit 6</code>而不是<code>reboot</code>命令,服务器会重新启动吗? ***</b></summary><br>

待续.

参考文档:

- [What differences it will make, if i use “telinit 6” instead of “reboot” command to restart my computer?](https://unix.stackexchange.com/questions/434560/what-differences-it-will-make-if-i-use-telinit-6-instead-of-reboot-command)

</details>

<details>
<summary><b>BSD系统中忘记了密码该怎么做?为什么要重启进入单用户模式?</b></summary><br>

重启系统,在`Boot:`提示符后输入`boot -s`来进入单用户模式.

关于shell的使用,确定按Enter显示#提示符.

输入`mount -urw /`来重新挂载根文件系统,再输入`mount -a`重新挂载全部文件系统.

输入`passwd root`来修改密码,最后运行`exit`重启.

**单用户模式**可以让你由root权限登录系统并修改任何内容.比如,使用单用户模式还原损坏的主数据库或系统数据库,或者更改服务器配置选项(例如密码恢复).

参考文档:

- [FreeBSD Reset or Recover Root Password](https://www.cyberciti.biz/tips/howto-freebsd-reset-recover-root-password.html)
- [Single User Mode Definition](http://www.linfo.org/single_user_mode.html)

</details>

<details>
<summary><b>如何在不使用文本编辑器的情况下修改文本?</b></summary><br>

比如:

```bash
# cat  >filename ... - overwrite file
# cat >>filename ... - append to file
cat > filename << __EOF__
data
__EOF__
```

</details>

<details>
<summary><b>如何增加或修改内核参数?有哪些内核参数需要调整?</b></summary><br>

在类Unix系统中设置内核参数,首先要编辑`/etc/sysctl.conf`文件,然后保存变更再执行`sysctl -p`命令,这样不用重启所有变更也会永久生效.

参考文档:

- [How to Change Kernel Runtime Parameters in a Persistent and Non-Persistent Way](https://www.tecmint.com/change-modify-linux-kernel-runtime-parameters/)

</details>

<details>
<summary><b>简述<code>/proc</code>文件系统.</b></summary><br>

`/proc`是一个虚拟文件系统,提供了关于内核,硬件和运行的进程的详细信息.

由于`/proc`包含虚拟文件,所以称之为虚拟文件系统.这些虚拟文件有特别的性质,其中的大多数都是零字节大小.

各虚拟文件中,`/proc/interrupts`,`/proc/meminfo`,`/proc/mounts`和`/proc/partitions`提供了系统硬件的实时信息,`/proc/filesystems`文件和`/proc/sys/`目录提供了系统配置信息和接口信息.

参考文档:

- [Linux Filesystem Hierarchy - /proc](https://www.tldp.org/LDP/Linux-Filesystem-Hierarchy/html/proc.html)

</details>

<details>
<summary><b>简介下数据备份方案.多久需要备份测试? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>简介ext3/ext4中的三种日志记录类型.</b></summary><br>

**ext3/ext4**文件系统中有下列三种日志记录类型:

- **Journal** - 元数据和数据同时记录在日志中
- **Ordered** - 只有元数据记录在日志中.当数据写入到磁盘之后才记录元数据.这是默认设置.
- **Writeback** - 只有元数据记录在日志中.在数据写入到磁盘之前或之后都有可能记录元数据.

</details>

<details>
<summary><b>什么是inode?如何查找和使用文件的inode编号?</b></summary><br>

**inode**是Linux和其他类Unix操作系统上的文件系统的一种数据结构,用来存储除了文件名和实际数据外的所有文件信息.数据结构是一种高效的数据存储方式.

Unix文件实际存储在磁盘上的两个不同部分:数据块和inode.暂不涉及超级块和其他更高深的信息.数据块存储了文件的内容,而关于该文件的信息存储在inode中.

文件的inode编号可以通过`ls`命令和`-i`选项来查找,该命令默认列出当前目录(用户当前工作目录)中的各对象(文件,链接和目录等).举个例子,下面的命令会显示当前目录中的各个对象和它们的inode:

```bash
ls -i
```

`df`的`-i`选项作用是提供每个文件系统上inode使用信息,而不是可用空间.具体来说,该命令会返回每个文件系统上的inode总数,可用inode数,已用inode数以及已用inode数的百分比.该选项可以和`-h`一起使用,使输出容易阅读,如下所示:

```bash
df -hi
```

**通过inodes查找文件**

如果知道inode,则可以通过find命令查找文件:

```bash
find . -inum 435304 -print
```

**删除文件名异常的文件**

有时在创建文件时使用了奇怪的字符作为文件名.在Unix文件系统中,除了null(ASCII 000)或"/"之外的其他字符都可以当作文件名.

用户可以用特殊字符创建文件或目录来使其难以被查看.比如在创建目录".."时在末尾添加一个空格,或者在文件名中包含一个退格:

```bash
touch `printf "aa\bb"`
```

使用`ls`可以看到:

```bash
ls
aa?b
ls | grep 'a'
ab
```

注意,当`ls`将结果发送到终端时,它会在文件名中用"**?**"来显示一个不可打印的字符.

可以通过`rm -i *`来删除该文件,该命令会在删除每个文件前要求你确认.当知道该文件的inode编号时,则可以通过`find`来删除文件:

```bash
ls -i
435304 aa?b
find . -inum 435304 -delete
```


参考文档:

- [Understand Unix/Linux Inodes Basics with Examples](https://www.thegeekstuff.com/2012/01/linux-inodes/)
- [What is an inode as defined by POSIX?](https://unix.stackexchange.com/questions/387087/what-is-an-inode-as-defined-by-posix/387093)

</details>

<details>
<summary><b><code>ls -l</code>显示的文件属性为问号.这意味着什么以及如何删除这些"僵尸"文件?</b></summary><br>

这个问题需要多个步骤,可能较难解决.有时会遇到下列问题:`test/file: Permission denied`,`test/file: No such file or directory`或`test/file: Input/output error`.

当用户无法对文件执行`stat()`(要有执行权限)时,会出现这种情况,但可以读取目录条目(要有访问权限).你可以看到目录中的文件列表,但无法读取文件来获得任何信息.

类似`rsync`这样的命令会在执行过程中生成临时文件,这些文件被快速创建和删除.如果使用简单的文件管理命令(`rm`,`mv`等)处理这些文件则会导致错误.

例子:

```bash
?????????? ? ?        ?               ?            ? sess_kee6fu9ag7tiph2jae
```

1) 修改权限: `chmod 0777 sess_kee6fu9ag7tiph2jae` 并尝试删除
2) 修改属组: `chown root:root sess_kee6fu9ag7tiph2jae` 并尝试删除
3) 修改目录权限和属组: `chmod -R 0777 dir/ && chown -R root:root dir/` 并尝试删除
4) 重新创建文件: `touch sess_kee6fu9ag7tiph2jae` 并尝试删除
5) 注意服务器上正在运行的进程中是否有类似`rsync`等的进程,当NFS服务器验证过载时可以看到这种瞬时错误.
6) 查找文件的inode: `ls -i`, 并尝试删除: `find . -inum <inode_num> -delete`
7) 重新挂载文件系统(如果可能)
8) 重启系统进入单用户模式并使用`fsck`修复文件系统

参考文档:

- [Question marks showing in ls of directory. IO errors too.](https://serverfault.com/questions/65616/question-marks-showing-in-ls-of-directory-io-errors-too)

</details>

<details>
<summary><b>要LVM还是不要?LVM的优点是什么?</b></summary><br>

- LVM让文件系统迁移变得非常容易
- 可以将卷组扩展到新的物理卷
- 可以从旧的物理卷移动任意数量的逻辑卷
- 无需卸载任何分区就可以从卷组中删除卷
- 可以制作逻辑卷的快照来进行备份
- LVM支持内置镜像,可以用多个物理卷上镜像一个逻辑卷
- LVM支持TRIM

参考文档:

- [What is LVM and what is it used for?](https://askubuntu.com/questions/3596/what-is-lvm-and-what-is-it-used-for)

</details>

<details>
<summary><b>如何增加LVM分区的大小?</b></summary><br>

使用`lvextend`命令调整LVM分区大小.

- 增加500M:

```bash
lvextend -L +500M /dev/vgroup/lvolume
```

- 增加所有可用的空间:

```bash
lvextend -l +100%FREE /dev/vgroup/lvolume
```

同时可以使用`resize2fs`或`xfs_growfs`来调整不同的文件系统:

- ext文件系统:

```bash
resize2fs /dev/vgroup/lvolume
```

- xfs文件系统:

```bash
xfs_growfs mountpoint_for_/dev/vgroup/lvolume
```

参考文档:

- [Extending a logical volume](https://www.tldp.org/HOWTO/LVM-HOWTO/extendlv.html)

</details>

<details>
<summary><b>什么是僵尸进程?</b></summary><br>

是一个已经完成执行过程的进程(通过`exit`系统调用),但在进程表中仍然存在:处于"**已终止状态**".

被标记为**defunct**的进程就是所谓的僵尸进程.由于它们的父进程没有正确地销毁它们,所以还是会存在.当父进程退出,init会销毁它们.

参考文档:

- [What is a <defunct> process, and why doesn't it get killed?](https://askubuntu.com/questions/201303/what-is-a-defunct-process-and-why-doesnt-it-get-killed)

</details>

<details>
<summary><b>在生产环境中升级/更新系统的正确流程是什么?这些流程自动化了吗?设置停机时间了吗? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>配置MySQL服务器时最后需要运行<code>sudo mysql_secure_installation</code>吗?</b></summary><br>

建议运行,它提供了很多安全选项,如:

- 可以为root帐户设置密码
- 可以删除可从本地主机外部访问的root帐户
- 可以删除匿名用户帐户
- 可以删除测试数据库,默认情况下,匿名用户可以访问该数据库

参考文档:

- [What is Purpose of using mysql_secure_installation?](https://stackoverflow.com/questions/20760908/what-is-purpose-of-using-mysql-secure-installation)

</details>

<details>
<summary><b>简介<code>kill</code>命令的常用方式.</b></summary><br>

说到停止进程,除非强制,否则绝不要使用`kill -9/SIGKILL`,这种野蛮的方式可能会导致问题.

建议总是使用下列方式:

- 首先,发送**SIGTERM**(`kill -15`)信号让进程关闭.常在干净关闭进程时使用(该信号可以被忽略).
- 其次,发送**SIGHUP**(`kill -1`)信号,该信号常用于让进程关闭和重启.该信号也可以被捕获和忽略.

绝大多数时候,这就足够了,而且更干净.

参考文档:

- [When should I not kill -9 a process?](https://unix.stackexchange.com/questions/8916/when-should-i-not-kill-9-a-process)
- [SIGTERM vs. SIGKILL](https://major.io/2010/03/18/sigterm-vs-sigkill/)

</details>

<details>
<summary><b><code>strace</code>命令是什么以及如何使用?如何用它来连接正在运行的进程?</b></summary><br>

`strace`是一个强大的命令行工具,用于在类Unix操作系统(如Linux)上进行调试和故障排除.它会捕获和记录进程发出的所有系统调用和收到的信号.

**Strace 概述**

`strace`可以当作是一个轻量级调试器.它可以通过监控系统调用和信号让程序员或用户快速理解程序和OS的交互过程.

**用处**

没有源代码或不想仔细检查一遍时.此外,使用自己的代码,对了解外部交互感兴趣又不想打开**GDB**时.

**追踪进程举例**

`strace -p <PID>` - 连接并追踪进程.

`strace -e trace=read,write -p <PID>` - 通过这种方式,还可以跟踪进程或程序的事务,如本例中的读取和写入.它会打印所有此类事务,包括进程的读写系统调用.

其他例子:

- `-e trace=network` - 追踪所有网络相关的系统调用.
- `-e trace=signal` - 追踪所有信号相关的系统调用.
- `-e trace=ipc` - 追踪所有IPC相关的系统调用.
- `-e trace=desc` - 追踪所有文件描述符相关的系统调用.
- `-e trace=memory` - 追踪所有内存映射相关的系统调用.

参考文档:

- [How should strace be used? (original)](https://stackoverflow.com/questions/174942/how-should-strace-be-used)
- [How does strace connect to an already running process? (original)](https://stackoverflow.com/questions/7482076/how-does-strace-connect-to-an-already-running-process)
- [strace: for fun, profit, and debugging](http://timetobleed.com/hello-world/)

</details>

<details>
<summary><b>什么时候使用访问控制列表而不是<code>chmod</code>命令? ***</b></summary><br>

待续.

</details>

<details>
<summary><b><code>/etc/shadow</code>支持哪些算法?</b></summary><br>

当前的经典算法:

- MD5
- SHA-1 (也称为SHA)

但上述两种都不建议继续用在加密/安全上.

- SHA-256
- SHA-512
- SHA-3 (KECCAK于2012年10月宣布在新的联邦批准哈希算法竞赛中获胜)

参考文档:

- [What is the algorithm used to encrypt Linux passwords?](https://crypto.stackexchange.com/questions/40841/what-is-the-algorithm-used-to-encrypt-linux-passwords)
- [How to find the hashing algorithm used to obfuscate passwords?](https://unix.stackexchange.com/questions/430141/how-to-find-the-hashing-algorithm-used-to-obfuscate-passwords)

</details>

<details>
<summary><b>在类Unix系统中ulimit的作用是什么?</b></summary><br>

大多数类Unix操作系统(包括Linux和BSD)都限制了每个进程或每个用户在系统资源(如线程,文件,网络连接等)上的使用数.这些**ulimits**可以避免单个用户使用了过多的系统资源.

</details>

<details>
<summary><b>什么是软限制和硬限制?</b></summary><br>

**硬限制**是超级用户或root设置的用户可用的最大值,在`/etc/security/limits.conf`文件中配置.用户需要更多资源的时候可以自行增加**软限制**,但**软限制**的值不能大于**硬限制**.

</details>

<details>

<summary><b>配置HAProxy来使用Redis时遇到错误:常规套接字错误(权限被拒绝).SELinux已启用.请通过CLI来处理这个SELinux基本问题.***</b></summary><br>

参考文档:

- [Basic SELinux Troubleshooting in CLI](https://access.redhat.com/articles/2191331)

</details>

<details>
<summary><b>已经配置RSA密钥登录,但服务器却显示<code>Server refused our key</code>,如何查找该问题?</b></summary><br>

**服务器端**

需要在`/etc/ssh/sshd_config`文件中配置`LogLevel VERBOSE`:

SSH认证失败记录下列文件中:`/var/log/auth.log`,`/var/log/secure`或`/var/log/audit/audit.log`.

以下命令可以查看ssh相关的日志行:

```bash
grep 'sshd' /var/log/auth.log
```

接下来,列出所有失败的SSH登录日志的命令:

```bash
grep "Failed password" /var/log/auth.log
```

该命令也行:

```bash
grep "Failed\|Failure" /var/log/auth.log
```

在较新的Linux发行版中可以使用`journalctl`命令来查询Systemd守护进程维护`ssh.service`或`sshd.service`时的日志文件,例如:

```bash
journalctl _SYSTEMD_UNIT=ssh.service | egrep "Failed|Failure"
```

**客户端**

在运行SSH客户端时加上`-v|--verbose`参数:这是第一级别的详细信息.不行的话,使用`-vv`来启用更高级别的调试详细信息.

参考文档:

- [Enable Debugging Mode in SSH to Troubleshoot Connectivity Issues](https://www.tecmint.com/enable-debugging-mode-in-ssh/)

</details>

<details>
<summary><b>项目主管需要一台SQL服务器.你会问他有什么要求? *</b></summary><br>

- 数据库会有多大?(是否可以在已有服务器上添加数据库)
- 数据库有多重要?(关于集群,灾难恢复,高可用性)

</details>

<details>
<summary><b>创建一个100行随机值的文件.</b></summary><br>

举例:

```bash
cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 100 > /path/to/file
```

</details>

<details>
<summary><b>如何不用密码就用其他用户运行脚本?</b></summary><br>

举例(使用`visudo`命令):

```bash
user1 ALL=(user2) NOPASSWD: /opt/scripts/bin/generate.sh
```

该命令必须是绝对路径!然后会从user1的shell执行`sudo -u user2 /opt/scripts/bin/generate.sh`就可以了.

</details>

<details>
<summary><b>如何检查bash脚本是否以root身份运行?</b></summary><br>

在bash脚本中,有多种方式来确认运行用户是不是root.

警告,不要通过用户名来确认用户是不是root,谁也不能保证ID是0的用户就是root,虽然这是一个广泛遵从的惯例,但任何人都可以把超级账户重命名为别的名字.

最佳方法是使用`$EUID`.`$UID`可以被更改,也不一定是运行脚本的实际用户.

```bash
if (( $EUID != 0 )); then
  echo "Please run as root"
  exit
fi
```

</details>

<details>
<summary><b>举例<code>nobody</code>账户的使用方法.<code>nobody</code>和<code>www-data</code>运行httpd服务时有什么区别?</b></summary><br>

在很多Unix系统中,`nobody`是用户账户的常规名称,它不拥有任何文件,没有特权组,没有任何其他功能.

用`nobody`来运行守护进程是很常见的,尤其在服务器中,可以降低控制`nobody`用户的恶意用户造成的损害.

但是,如果用`nobody`来运行多个守护进程,会降低其可用性.因为`nobody`运行的进程能互相发送信号,互相调试,读取或修改彼此的内存,所以获得其中一个守护进程的控制即获得了全部守护进程的控制.

**什么时候使用`nobody`账户?**

当程序的操作不需要权限时.This is most notable when there isn't ever going to be any disk activity.

实例是**memcached**(一个键值缓存/数据库),在我的服务器上用`nobody`账户运行着.为什么?因为它不需要任何权限只要给它一个有写文件权限的账户就行,而这是一个没有风险的事.

web服务器也是好例子.想象一下,如果Apache以root身份运行,并且有人发现可以通过Apache向控制台发送自定义命令,从而能够访问整个系统.

`nobody`账户也用于让用户有文件系统权限但禁止用户登录shell,这样可以防止用户执行任务.

**httpd(Apache)上的`nobody`或`www-data`**

在启动Apache时需要root权限,但它会马上转移到另一个没有权限的用户.比如`nobody`,`apache`或`www-data`.

有些程序使用`nobody`作为默认启动用户.例如,您可能不会想让Apache服务把属于bind服务的文件覆写了,所以每个服务都有一个对应的账户是很好的主意.

让Apache以`nobody:nobody`运行非常简单,只需要设置用户和组即可.但正如上述,不建议指定用户/组.因为很可能在将来添加另一个用`nobody`运行的服务,然而会忘记已经把文件系统的写权限授予了`nobody`用户.

如果`nobody`变的不可靠了,其影响力可能比程序隔离用户(如`www-data`)更大.当然这很大程度上都取决于文件和组的权限.当程序区分用户是否能读取文件时,`nobody`可以通过,但其他用户将被拒绝.

参考文档:

- [What is nobody user and group?](https://unix.stackexchange.com/questions/186568/what-is-nobody-user-and-group)
- [The Linux and Unix Nobody User](http://linuxg.net/the-linux-and-unix-nobody-user/)
- [What is the purpose of the 'nobody' user?](https://askubuntu.com/questions/329714/what-is-the-purpose-of-the-nobody-user)

</details>

<details>
<summary><b>有什么方法可以将输出重定向到文件并显示在标准输出上?</b></summary><br>

使用`tee`命令:

`foo | tee output.file`

如果需要标准输出:

`ls -a | tee output.file`

如果需要包括错误输出:

`program [arguments...] 2>&1 | tee outfile`

`2>&1`表示将通道2(stderr/错误输出)重定向并合并到通道1(stdout/标准输出),同时通过`tee`命令输出到指定文件.

如果需要添加到日志文件:

`program [arguments...] 2>&1 | tee -a outfile`

</details>

<details>
<summary><b>bash的首选shebang(#!)是什么以及为什么?使用<code>./script</code>或 <code>bash script</code>来执行文件的区别是什么?</b></summary><br>

你应该使用`#!/usr/bin/env bash`来实现可移植性:不同的*nixes操作系统会把bash放在不同的位置,而使用 **/usr/bin/env** 可以保证运行的bash是在`PATH`上找到的第一个.

运行`./script`需要对该文件有执行权限,但不知道程序具体是什么类型,它可能是bash脚本,sh脚本或Perl, Python,awk,expect脚本,或一个可执行的二进制文件.而`bash script`则强制它在sh下运行,而不是其他东西.

参考文档:

- [What is the preferred Bash shebang? (original)](https://stackoverflow.com/questions/10376206/what-is-the-preferred-bash-shebang)

</details>

<details>
<summary><b>需要运行的命令会持续很长时间,如何防止ssh会话丢失导致进程终止?</b></summary><br>

使用`nohup`让进程忽略挂起信号:

```bash
nohup long-running-process &
exit
```

或者使用GNU窗口:

```bash
screen -d -m long-running-process
exit
```

参考文档:

- [5 Ways to Keep Remote SSH Sessions and Processes Running After Disconnection](https://www.tecmint.com/keep-remote-ssh-sessions-running-after-disconnection/)

</details>

<details>
<summary><b>中级认证机构的主要作用是什么?</b></summary><br>

要了解中级CA的主要作用,首先要了解**根CAs**,**中级CAs**和**SSL证书信任链**.

**根CAs**是主要CAs,它一般不直接签署最终的实体/服务器证书而是颁发根证书,这些证书通常被预装在所有浏览器,移动设备和应用程序中,其私钥用于签署其他后续证书如中间证书.根证书通常是"离线"状态并处于高度安全的环境中,访问受到严格限制.

**中间CAs**是隶属于一个或多个级别的根CA的CAs,被授权来代表根CA签署证书.创建和使用中间CAs的主要是为了安全性,如果中间私钥被泄露了,根CA可以撤销中间证书并使用新的加密密钥来创建新的证书.

**SSL证书信任链**是一组SSL证书列表,从根证书到最终实体/服务器证书.要让SSL证书被信任,必须由被信任的CA颁发,且该被信任的CA在连接设备中(浏览器,移动设备和应用程序)的可信CA列表中.于是,该连接设备会测试信任链中的每个SSL证书的可信度,直到它与可信CA颁发的SSL证书匹配为止.

**根-中间CA**结构由每个主要CA创建,用来防止根密钥泄露带来的灾难性影响.如果根密钥被泄露,会导致根证书和所有从属证书都不可信.因此,创建中间CA是严格保护根密钥的最佳实践.

参考文档:

- [How certificate chains work](https://knowledge.digicert.com/solution/SO16297.html)

</details>

<details>
<summary><b>配置变更后如何重启PostgreSQL?</b></summary><br>

情景1:

```bash
systemctl reload postgresql
```

情景2:

```
su - postgres
/usr/bin/pg_ctl reload
```

情景3:

```
SELECT pg_reload_conf();
```

</details>

<details>
<summary><b>在<code>.profile</code>中添加了几个别名.如何立即生效但不退出shell?</b></summary><br>

最好的方法是`exec $SHELL -l`,exec可以用一个新进程替换当前进程.

其他比较好的方法是`. ~/.profile`.

参考文档:

- [How to reload .bash_profile from the command line?](https://stackoverflow.com/questions/4608187/how-to-reload-bash-profile-from-the-command-line)

</details>

<details>
<summary><b>如何退出shell但不保存历史命令记录?</b></summary><br>

```bash
kill -9 $$
```

or

```bash
unset HISTFILE && exit
```

参考文档:

- [How do I close a terminal without saving the history?](https://unix.stackexchange.com/questions/25049/how-do-i-close-a-terminal-without-saving-the-history)

</details>

<details>
<summary><b>什么是UID为0叫toor的账户?是被入侵了吗?</b></summary><br>

**toor**是一个超级账户root的替代,由root反着拼写而来.它主要用在非标准的shell上,所以在root使用的默认shell上不需要修改.

因为shells不是基础发行版自带的,而是通过端口或安装包默认安装在`/usr/local/bin`中.如果root的shell在`/usr/local/bin`中,而包括`/usr/local/bin`的文件系统没有挂载,那root就登陆不了,需要重启进入单用户模式来解决问题.

有人在非标准shell用toor处理日常任务,而将root和标准shell用在单用户模式或紧急情况.默认情况下,toor没有密码,用户无法直接登陆,需要用root为它设置密码后,再用来登陆.

参考文档:

- [The root account (and toor)](https://administratosphere.wordpress.com/2007/10/04/the-root-account-and-toor/)

</details>

<details>
<summary><b>有没有一种简单的方法从复杂目录结构里的1000个文件中查找包含特定字符串的文件?</b></summary><br>

使用`fgrep`:

```bash
fgrep * -R "string"
```

或:

```bash
grep -insr "pattern" *
```

- `-i` 忽略**PATTERN**和输入文件中的大小写
- `-n` 为每行输出前添加前缀,该前缀为文件中该字符串所在的行数
- `-s` 禁止有关不存在或不可读文件的错误消息
- `-r` 以递归方式读取每个目录下的所有文件

参考文档:

- [How to grep a string in a directory and all its subdirectories files in LINUX?](https://stackoverflow.com/questions/15622328/how-to-grep-a-string-in-a-directory-and-all-its-subdirectories-files-in-linux)

</details>

<details>
<summary><b>如何查找的命令运行时加载了哪些链接的动态库文件?</b></summary><br>

使用`ldd`命令

```bash
ldd /bin/ls
```

</details>

<details>
<summary><b>有个同步测试环境和生产环境的任务,需要哪些步骤?</b></summary><br>

这很容易进入克隆环境的误区而忽视了本质:

- 只有生产环境才是生产环境

每次部署的时候,都是在测试部署一份独一无二的代码+软件+环境组合.

一个比较好的解决方案是定期克隆生产服务器来创建测试服务器.使用快照在dev/test中创建生产环境的完全复制实例,如下:

- 生成生产环境快照
- 将快照复制到新的环境
- 使用此快照创建新磁盘

当然,也可以克隆各种系统组件或整个系统,并获取实际流量在离线环境下重现(系统测试的黄金标准).但是很多系统都过于庞大复杂,克隆成本过高.

在环境同步之前,一个好方法是跟踪对测试环境做的每项更改,并将其转发到生产环境,这样就不会漏掉任何步骤且顺利地完成.

使用结构比较工具或部署脚本来将生产环境更新到测试环境也是一个很好的解决方案.

**同步前工作**

首先是告知开发人员和客户不要对测试环境进行更改(可以的话,禁用目标测试环境域名或设置提示同步信息的静态页面).

创建两种环境的备份/快照也很重要.

**数据库服务器**

- 同步/更新系统版本(比如包)
- 从生产数据库服务器上的数据库创建dump文件
- 把dump文件导入测试数据库服务器
- 必要的话,同步登陆权限,角色,数据库权限,数据库连接数等.

**应用服务器**

- 同步/更新系统版本(比如包)
- 必要的话,更新内核参数,防火墙规则等
- 同步/更新所有正在运行/重要的服务的配置文件
- 同步/更新用户帐户(如权限)及其主目录
- 使用git/svn存储库部署项目
- 同步/更新项目中的重要目录,如**static**,**asset**等
- 同步/更新项目目录的权限
- 删除/更新所有webhooks
- 更新cron作业

**其他工作**

- 更新测试域名和特定URL的负载均衡配置
- 更新队列,会话和存储实例的配置

参考文档:

- [Keeping testing and production server environments clean, in sync, and consistent](https://stackoverflow.com/questions/639668/keeping-testing-and-production-server-environments-clean-in-sync-and-consisten)

</details>

###### 网络问题 (24)

<details>
<summary><b>在工作站上配置一个虚拟接口. ***</b></summary><br>

待续.

</details>

<details>
<summary><b>根据HTTP监控,网站宕机,但能telnet到端口,该如何解决?</b></summary><br>

如果可以telnet到端口,这表示监听该端口的服务正在运行,你可以连接到它(这不是一个网络问题).最好先检查域名能否被解析成IP地址,再使用该域名来测试连接.

首先检查网站在其他地理位置是否在线.这会让你知道该网站是否在任何地方都已宕机,还是只有你的网络无法查看.检查web浏览器返回的内容也是一个好主意.

**如果只有IP能连接**

- 可以使用whois查看DNS服务器为站点提供主机名的内容:`whois www.example.com`
- 可以使用`dig`或`host`等工具来测试DNS以查看主机名是否正常解析:`host www.example.org dns.example.org`
- 还可以检查全局的公共DNS服务器:`host www.example.com 9.9.9.9`

如果域名解析不了那么问题出在DNS服务器上.

**如果域名解析正常**

- 查询日志文件并解决日志文件中显示的问题,这也是找问题的最佳方案
- 检查http状态码,通常是5xx的响应状态码,这表示可能是服务器由于客户端连接过多导致过载或缓存规则没有生效
- 检查网站/代理服务器的配置(如`nginx -t -c </path/to/nginx.conf>`),或许是别的管理员修改了域名配置
- 或许服务器上的空间或内存不足导致有些服务崩溃了
- 或许网站的代码出错了

</details>

<details>
<summary><b>负载均衡会明显影响服务器的性能.简析几种负载均衡的机制. ***</b></summary><br>

待续.

</details>

<details>
<summary><b>简介几种可以在DNS出问题时使用的网络故障修复工具. ***</b></summary><br>

待续.

</details>

<details>
<summary><b>简析HTTP 1.1和HTTP 2.0之间的区别.</b></summary><br>

<b>HTTP/2</b>支持多路复用请求,标头压缩,优先级和更智能的数据包流管理.这样可以减少延迟并加速下载现代网页上的内容.

与**HTTP/1.1**的主要区别:

- 它是二进制的,而不是文本
- 完全多路复用,而不是有序和阻塞
- 可以使用一个连接来实现并发
- 使用标头压缩来减少开销
- 允许服务器主动将响应"推送"到客户端缓存中

参考文档:

- [What is HTTP/2 - The Ultimate Guide](https://kinsta.com/learn/what-is-http2/)

</details>

<details>
<summary><b>开发团队报告错误:<code>POST http://ws.int/api/v1/Submit/ resulted in a 413 Request Entity Too Large</code>. 怎么办?</b></summary><br>

**修改该域名下的NGINX配置**

设置正确的`client_max_body_size`变量值:

```bash
client_max_body_size 20M;
```

重启Nginx.

**修改php.ini文件中的上传限制**

不是必要的,但最好修改PHP的配置确保上传没有超出php的限制.

先找到下列配置项:

```bash
upload_max_filesize
post_max_size
```

将数量修改为20M,默认是8M和2M:

```bash
upload_max_filesize = 20M
post_max_size = 20M
```

最后保存并重启PHP.

参考文档:

- [413 Request Entity Too Large in Nginx with client_max_body_size set](https://serverfault.com/questions/814767/413-request-entity-too-large-in-nginx-with-client-max-body-size-set)

</details>

<details>
<summary><b>什么是握手机制,为什么需要3次握手?</b></summary><br>

**握手**开始于一台设备向另一台设备发送信息表明它想建立通信通道时,之后这两个设备来回发送一些消息确保它们能够就通信协议达成一致.

**三次握手**是一种在TCP/IP网络中的本地主机/客户端和服务器之间建立连接的方法.它有三个步骤,要求客户端和服务端在实际数据通信前先交换`SYN`和`ACK`(`SYN`,`SYN-ACK`,`ACK`)数据包.

参考文档:

- [Why do we need a 3-way handshake? Why not just 2-way?](https://networkengineering.stackexchange.com/questions/24068/why-do-we-need-a-3-way-handshake-why-not-just-2-way)

</details>

<details>
<summary><b>为什么UDP比TCP快?</b></summary><br>

**UDP**比**TCP**快是因为它没有需要确认的数据包(`ACK`)来允许一个持续的数据包流,而**TCP**需要确认一组通过**TCP**窗口大小和往返时间计算出来的数据包.

参考文档:

- [UDP vs TCP, how much faster is it?](https://stackoverflow.com/questions/47903/udp-vs-tcp-how-much-faster-is-it)

</details>

<details>
<summary><b>在你看来,哪5个重要的OpenSSH参数可以提高其安全性? ***</b></summary><br>

待续.

参考文档:

- [OpenSSH security and hardening](https://linux-audit.com/audit-and-harden-your-ssh-configuration/)

</details>

<details>
<summary><b>什么是NAT?它用来做什么?</b></summary><br>

它可以让内部网络中的私有IP地址连接Internet.**NAT**工作在路由上,通常连接两个网络,并在数据包转发到别的网络前将内部网络中的私有地址(非全局唯一)转换为合法地址.

**NAT**可以分配特定的外部地址给需要访问外部网络的工作站或计算机,从而能用一个唯一的公网IP地址和其他计算机或应用通信.**NAT**也是防火墙安全的一个非常重要的方面.

参考文档:

- [Network Address Translation (NAT) Concepts](http://www.firewall.cx/networking-topics/network-address-translation-nat/227-nat-concepts.html)

</details>

<details>
<summary><b>生成树协议的目的是什么?</b></summary><br>

该协议工作于OSI模型的第二层,目的是防止网络产生环路.如果没有**STP**,部署冗余交换机会产生广播风暴破坏最强大的网络.

</details>

<details>
<summary><b>如何查看在Linux服务器上正在监听的端口?</b></summary><br>

使用下列命令:

- `lsof -i`
- `ss -l`
- `netstat -atn` - for tcp
- `netstat -aun` - for udp
- `netstat -tulapn`

</details>

<details>
<summary><b>连接远程主机时显示<code>Host key verification failed</code>意味着什么?你自动接受了吗?</b></summary><br>

`Host key verification failed`表示远程主机的主机密钥已经更改.当连接到一台`/etc/ssh`中的主机密钥已更改的计算机时(如该计算机已升级但没有复制其旧的主机密钥),容易发生这种情况.当使用ssh重新连接远程主机时,主机密钥是用来证明这是第一次访问时所连接的那台主机的证据.

首次通过SSH连接到服务器时,会将该服务器的公钥存储在本机主目录中(如果使用Mac或Windows则可能存储在设置的本地帐户)的**known_hosts**文件.当重新连接到该服务器时,SSH连接将验证当前公钥是否与在**known_hosts**文件中保存的公钥相匹配.如果自上次连接服务器后服务器密钥已更改,将收到上述错误.

不要听建议删除整个**known_hosts**文件,这会取消警报,导致产生中间人攻击时没有警告提示.

在接受新主机密钥之前,请先与系统管理员联系来进行验证.

参考文档:

- [Git error: "Host Key Verification Failed" when connecting to remote repository](https://stackoverflow.com/questions/13363553/git-error-host-key-verification-failed-when-connecting-to-remote-repository)

</details>

<details>
<summary><b>如何通过<code>telnet</code>发送HTTP请求?</b></summary><br>

如下:

```bash
telnet example.com 80
Trying 192.168.252.10...
Connected to example.com.
Escape character is '^]'.
GET /questions HTTP/1.0
Host: example.com

HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
...
```

</details>

<details>
<summary><b>如何在Linux上停止使用特定端口(如80)的程序?</b></summary><br>

列出所有监听80端口的进程:

```bash
# with lsof
lsof -i:80

# with fuser
fuser 80/tcp
```

停止所有监听80端口的进程:

```bash
kill $(lsof -t -i:80)
```

比较暴力的:

```bash
kill -9 $(lsof -t -i:80)
```

使用`fuser`命令:

```bash
fuser -k 80/tcp
```

参考文档:

- [How to kill a process running on particular port in Linux?](https://stackoverflow.com/questions/11583562/how-to-kill-a-process-running-on-particular-port-in-linux/32592965)
- [Finding the PID of the process using a specific port?](https://unix.stackexchange.com/questions/106561/finding-the-pid-of-the-process-using-a-specific-port)

</details>

<details>
<summary><b>报错<code>curl: (56) TCP connection reset by peer</code>.如何解决这个问题?</b></summary><br>

- 检查URL是否正确,也许应该添加`www`或设置正确的`Host`头部?格式也要检查下.
- 检查域名是否能被解析为正确的IP地址
- 使用`--trace-ascii curl.dump`来启用调试.`Recv failure`是一个常见的错误,很难获得更多信息
- 使用`--proxy`启用外部代理来调试与外部ip的连接
- 使用网络嗅探器(如`tcpdump`)在较低的TCP/IP层中进行连接调试
- 检查生产环境和网络出口点的防火墙规则,还有NAT规则
- 检查网络中传输的数据包的MTU大小
- 如果连接https协议,使用`curl`命令的ssl/tls参数检查SSL版本
- 也可能是客户端的问题,如netfilter会丢弃或限制从你的IP地址到域名的连接

参考文档:

- [CURL ERROR: Recv failure: Connection reset by peer - PHP Curl](https://stackoverflow.com/questions/10285700/curl-error-recv-failure-connection-reset-by-peer-php-curl)

</details>

<details>
<summary><b>如何使用防火墙允许来自特定IP的流量或发送流量到特定IP?</b></summary><br>

如下:

```bash
/sbin/iptables -A INPUT -p tcp -s XXX.XXX.XXX.XXX -j ACCEPT
/sbin/iptables -A OUTPUT -p tcp -d  XXX.XXX.XXX.XXX -j ACCEPT
```

</details>

<details>
<summary><b>如何在OpenBSD上使用<code>pf</code>拉黑特定IP?</b></summary><br>

最佳方法是在`pf.conf`文件中定义一个表并创建一个阻止主机的规则:

```bash
table <badhosts> persist
block on fxp0 from <badhosts> to any
```

然后在其中动态添加/删除IP地址:

```bash
pfctl -t badhosts -T add 1.2.3.4
pfctl -t badhosts -T delete 1.2.3.4
```

</details>

<details>
<summary><b>像Apache或Nginx这样的web服务器何时将信息写入日志文件?在提交请求前还是后?</b></summary><br>

这两种web服务器都提供了非常全面和灵活的日志记录功能 - 用于记录服务器上发生的所有事情,从初始请求到URL匹配过程,再到最后连接的方式,包括了该流程中可能发生的任何错误.

**Apache**

Apache服务器访问日志记录服务器处理的所有请求(在请求完成之后).

**Nginx**

NGINX在处理请求后立即在访问日志中写入有关客户端请求的信息.

参考文档:

- [When does Apache log to access.log - before or after serving the request?](https://webmasters.stackexchange.com/questions/65566/when-does-apache-log-to-access-log-before-or-after-serving-the-request)
- [nginx log request before processing](https://serverfault.com/questions/693049/nginx-log-request-before-processing)

</details>

<details>
<summary><b>分析web服务器日志发现只有<code>5xx</code>http状态码.该使用什么工具?</b></summary><br>

```bash
tail -n 100 -f /path/to/logfile | grep "HTTP/[1-2].[0-1]\" [5]"
```

http/https日志管理工具举例:

- **goaccess** - 是一个开源的实时web日志分析和交互式查看工具,可以在*nix系统中的终端或浏览器运行
- **graylog** - 是一个免费的开源日志管理平台,支持深层次的日志收集和分析

参考文档:

- [Best Log Management Tools: 51 Useful Tools for Log Management, Monitoring, Analytics, and More](https://stackify.com/best-log-management-tools/)

</details>

<details>
<summary><b>为什么开发人员通过ssh使用服务器的私钥来部署应用的行为是不对的?这种情况下有什么更好的解决方案吗?</b></summary><br>

你拥有个人账户的私钥,服务器需要你的公钥来验证你当前账户的私钥是否有授权.

私钥的重要在于它们是私有的,这意味着只有你拥有私钥.如果有人接管了你的私钥,那它就能够随时冒充你.

一个更好的解决方案是使用ssh密钥转发.举个例子,先创建一个`~/.ssh/config`文件.然后添加主机(域名或IP地址,并设置`ForwardAgent yes`).如下:

```bash
Host git.example.com
    User john
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa.git.example.com
    ForwardAgent yes
```

远程服务器必须允许入站连接能转发SSH代理,且本地的`ssh-agent`必须正在运行.

当然转发ssh代理有一定风险,如果远程计算机上的某个人可以访问转发你的ssh代理连接,他们仍然可以使用你的密钥.不过,这比在远程计算机上存储密钥要好:攻击者只能使用ssh代理连接,而不能使用密钥本身.因此,只有在你登录远程计算机时,他们才能做任何事情.如果将密钥存储在远程计算机上,他们可以随时复制并使用它.

如果你使用ssh密钥,强烈建议使用口令来降低密钥泄漏的风险.

参考文档:

- [How to forward local keypair in a SSH session?](https://stackoverflow.com/questions/12257968/how-to-forward-local-keypair-in-a-ssh-session)
- [Using SSH agent forwarding](https://developer.github.com/v3/guides/using-ssh-agent-forwarding/)
- [SSH Agent Forwarding considered harmful](https://heipei.github.io/2015/02/26/SSH-Agent-Forwarding-considered-harmful/)
- [Security Consideration while using ssh-agent](https://www.commandprompt.com/blog/security_considerations_while_using_ssh-agent/)

</details>

<details>
<summary><b>CORS和CSPs的区别是什么?</b></summary><br>

**CORS**允许域名放宽**同源策略**.

比如说如果用户同时登录了`example.com`和`example.org`,那么同源策略会阻止`example.com`向`example.org/current_user/full_user_details`发出AJAX请求并获得响应的访问.

这是web的默认策略,可防止用户在同时登录多个站点时泄露数据.

使用**CORS**后,`example.org`可以设置一个策略,允许源`https//example.com`读取由AJAX对它的请求和响应.如果`example.com`和`example.org`由同一家公司运营并且在用户的浏览器中允许它们数据共享,则可以这样做.它只影响客户端方面,而非服务器端.

另一方面,**CSPs**设定了当前站点上可以运行的内容的策略.比如,如果允许内嵌的JavaScript执行,或者加载其他域的`.js`文件,这会导致攻击者尝试将脚本注入HTML页面从而受到**XSS**攻击,该策略可以阻止内嵌脚本执行,从根本挫败攻击.

参考文档:

- [What is the difference between CORS and CSPs? (original)](https://stackoverflow.com/questions/39488241/what-is-the-difference-between-cors-and-csps)
- [CSP, SRI and CORS](https://colorblindprogramming.com/csp-sri-and-cors)

</details>

<details>
<summary><b>简析使用<code>nmap</code>扫描时从防火墙返回的四种响应类型.</b></summary><br>

可能有四种类型的响应:

- **Open port** - 由于防火墙的关系开放端口会很少
- **Closed port** - 由于防火墙的关系大部分是关闭端口
- **Filtered** - `nmap`不确定该端口是否打开
- **Unfiltered** - `nmap`可以访问端口,但仍然不确定该端口的具体状态

参考文档:

- [NMAP - Closed vs Filtered](https://security.stackexchange.com/questions/182504/nmap-closed-vs-filtered)

</details>

<details>
<summary><b><code>tcpdump</code>的作用是什么?如何只捕获接口的传入流量?</b></summary><br>

`tcpdump`是功能最强大且使用最广泛的命令行数据包嗅探器或数据包分析器工具,用于捕获或过滤在网络中的特定接口接收或传输的TCP/IP数据包.

`tcpdump`使网卡进入混杂模式,这会让它接收它收到的每个数据包.它允许用户查看所有通过网络传递的流量.Wireshark使用pcap捕获数据包.

如果只想捕获接口的传入流量:

- `-Q in` - Linux上的`tcpdump`版本
- `-D in` - BSD上的`tcpdump`版本

两个参数都设置了应该捕获的数据包的发送/接收方向.

```bash
tcpdump -nei eth0 -Q in host 192.168.252.125 and port 8080
```

</details>

###### Devops问题 (7)

<details>
<summary><b>最流行的DevOps工具是什么?你使用过哪些?</b></summary><br>

最流行的DevOps工具如下:

- **Git** : 版本控制系统工具
- **Jenkins** : 持续集成工具
- **Selenium** : 持续测试工具
- **Puppet**, **Chef**, **Ansible** : 配置管理和部署工具
- **Nagios** : 持续监控工具
- **Docker** : 容器化工具

</details>

<details>
<summary><b>上面那些工具是如何一起工作的?</b></summary><br>

- 开发人员开发代码,源代码由Git等版本控制系统工具管理
- 开发人员将代码发送到Git存储库,并且该代码中所做的任何更改都将提交到此存储库
- Jenkins使用Git插件从存储库中拉取此代码,并使用Ant或Maven等工具构建它
- 配置管理工具如puppet用来部署和配置测试环境,然后Jenkins在测试环境中发布此代码,并使用selenium等工具进行测试
- 一旦代码被测试完毕,Jenkins将其发送到生产服务器上进行部署(生产服务器也由puppet等工具部署和维护)
- 部署后通过Nagios等工具持续监控
- Docker容器提供测试环境来测试构建后的功能

</details>

<details>
<summary><b>Ansible中的playbooks是什么?</b></summary><br>

Playbooks是Ansible的配置,部署和编排语言.

它可以描述你希望远程服务器实施的策略,或一般IT流程中的一系列步骤.Playbooks被设计为强可读的并以基本文本语言开发.

一般情况下,可以使用playbooks来管理远程服务器的配置和部署.

</details>

<details>
<summary><b>Nagios中的NRPE(Nagios Remote Plugin Executor)是什么?</b></summary><br>

**NRPE**插件允许你在远程Linux/Unix服务器上执行Nagios插件.这样做才能让Nagios监视远程服务器上的"本地"资源(如CPU负载,内存使用情况等).

由于这些公共资源通常不会暴露给外部服务器,因此必须在远程Linux/Unix服务器上安装**NRPE**等代理程序.

</details>

<details>
<summary><b>Nagios中的主动检查和被动检查有什么区别?</b></summary><br>

主动检查和被动检查之间的主要区别在于主动检查由Nagios启动和执行,而被动检查由外部应用程序执行.

被动检查对于监视以下服务非常有用:

- 异步性质,无法通过定期轮询其状态来有效监控.
- 位于防火墙后面,无法从监控主机主动检查.

主动检查的主要功能如下：

- Nagios流程启动主动检查.
- 定期运行主动检查.

</details>

<details>
<summary><b><code>git clone</code>如何包括子模块?</b></summary><br>

如下:

```bash
# 使用-j8选项
git clone --recurse-submodules -j8 git://github.com/foo/bar.git

# 对于已经克隆的repos或较旧的Git版本
git clone git://github.com/foo/bar.git
cd bar
git submodule update --init --recursive
```

</details>

<details>
<summary><b>使用Redis的优势是什么?什么是<code>redis-cli</code>?</b></summary><br>

- 速度快(比其他工具快得多)
- 支持服务端锁定
- 有很多客户端库
- 具有命令级别的原子操作(tx操作)
- 支持散列,集合,位图等丰富的数据类型

`redis-cli`是**Redis**的命令行界面,一个简单的程序用来向**Redis**发送命令,并直接在终端上展示服务端返回的回复.

参考文档:

- [10 Advantages of Redis](https://dzone.com/articles/10-traits-of-redis)

</details>

###### 网络安全问题 (4)

<details>
<summary><b>什么是XSS,如何避免?</b></summary><br>

**Cross Site Scripting**是web应用程序中的JavaScript漏洞.简单解释就是当用户在客户端输入表单中输入脚本后,该脚本不需要确认就能直接执行.这会导致不受信任的数据在客户端保存并执行.

XSS的对策是输入验证,实施CSP(内容安全策略)等.

</details>

<details>
<summary><b>HIDS和NIDS哪个更好,为什么?</b></summary><br>

**HIDS**是主机入侵检测系统,**NIDS**是网络入侵检测系统.两个系统的功能都差不多,只是目标不同.**HIDS**放置在每个主机上,而**NIDS**放置在网络中.对于企业来说,**NIDS**是首选,因为**HIDS**难以管理,而且它也会消耗主机的处理能力.

</details>

<details>
<summary><b>什么是合规性?</b></summary><br>

遵守由政府/组织制定的一套标准.例如:存储,处理或传输支付相关信息的行业需要遵守PCI DSS(支付卡行业数据安全标准).其他合规性示例可以是符合其自身政策的组织.

</details>

<details>
<summary><b>什么是WAF,它有哪些类型?</b></summary><br>

**WAF**是web应用程序防火墙.它通过过滤合法流量中的恶意流量的来保护应用程序.**WAF**可以是box型或基于云型.

</details>

### :diamond_shape_with_a_dot_inside: 高级系统管理员

<details>
<summary><b>简述你当前负责的系统架构.并说说它还有什么可扩展的或容错的地方 ***</b></summary><br>

待续.

</details>

<details>
<summary><b>说说你们当前生产环境是怎么部署代码的. ***</b></summary><br>

待续.

</details>

<details>
<summary><b>简析内核的不同类型.</b></summary><br>

**单内核**

在此类内核结构的早期阶段,所有基本系统服务(如进程和内存管理,中断处理等)都打包到内核空间中的单个模块中.这种类型的结构导致了一些严重的缺点,如:

- 内核变得非常大
- 可维护性差,修复错误或添加新功能需要重新编译整个内核,这可能会耗费数小时

在现代的单内核结构中,内核由可以动态加载或卸载的不同模块组成.这种模块化结构可以轻松扩展操作系统的功能,并使内核的可维护性变得非常容易.每当特定的内核模块发生更改或需要修复时,只需要加载或卸载相关模块就可以了.

Linux使用单内核结构.

**微内核**

这种结构主要为了解决不断增长的内核代码大小的问题,在单内核结构中我们无法对其进行控制.该结构允许一些基本服务(如设备驱动管理,协议栈,文件系统等)在用户空间中运行.

在该结构中,所有系统基本服务作为用户空间的一部分以特殊的用户态程序:服务器运行,系统中的其他程序通过进程间通信(IPC)来使用这些服务器.

比如说,我们有用于设备驱动程序,网络协议堆栈,文件系统,图形等的服务器.除了那些内核授予特权用来与物理内存部分交互的程序外,微内核的服务器本质上是守护程序.

PS:微内核的例子有AIX,BeOS,L4微内核系列,Mac OS X,Minix,MorphOS,QNX,RadiOS,VSTa等

**混合内核(模块化内核)**

这是上述两者的组合,其关键思想是操作系统服务在内核空间中,并且在用户空间中的服务没有消息传递,没有性能开销,没有可靠性保障.

Microsoft的NT内核,到最新的Windows版本都使用这种内核结构.

参考文档:

- [An Introduction to Kernels. The Heart of Computing Devices. (original)](https://keetmalin.wixsite.com/keetmalin/single-post/2017/08/24/An-Introduction-to-Kernels-The-Heart-of-Computing-Devices)

</details>

<details>
<summary><b>程序报错缺少库.如何提供动态链接库?</b></summary><br>

环境变量`LD_LIBRARY_PATH`是一组由冒号分隔的目录.在搜索标准库目录之前会先搜索这个目录.这在调试新库或使用用于特殊目的非标准库时非常有用.

使用`LD_LIBRARY_PATH`的最佳方法是在执行程序之前先在命令行或脚本上设置它.这样,新的`LD_LIBRARY_PATH`与系统的就隔离开来了.

使用用例:

```bash
export LD_LIBRARY_PATH="/list/of/library/paths:/another/path" ./program
```

参考文档:

- [How to correctly use LD_LIBRARY_PATH](http://wiredrevolution.com/system-administration/how-to-correctly-use-ld_library_path)

</details>

<details>
<summary><b>新手管理员需要知道的安全使用root权限的规则有哪些? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>跨系统同步UID/GID的优点是什么?</b></summary><br>

在网络中统一管理**user/UID**和**group/GID**有以下几方面原因:

首先很明显 - 它方便管理用户.

如果每个用户都希望对整个网络中的系统具有相对统一的访问权限,那么他们也会希望相同的用户名和密码可以在每个系统上使用.如果他们更改了密码,他们会希望这种变化是全局性的.

它还与Unix和Linux中的用户名和组名有关系.它们被映射为数字形式(分别是**UID**和**GID**).从内核到驱动程序所有文件的所有权(inode)和进程都使用这些数字来识别访问和身份.这些数值通过utilities反向映射回其对应的名称来显示或处理信息.

另外建议采取唯一**UID's**的策略,当用户退出时,你可以将他的**UID**"退休"(可以通过将用户移除组,设置用户"shell"为`/bin/denied`并将其主目录标为_graveyard_来禁止用户登陆).

这么做的原因是如果你要维护存档备份数年(或无限期),你会希望避免以下情况导致的混乱和混淆:恢复一个(已久的)用户的文件并发现其现在属于一个新用户.

参考文档:

- [UID/GID Synchronization and Management (original)](https://linuxgazette.net/issue31/tag_uidgid.html)
- [What's the advantage of synchronizing UID/GID across Linux machines?](https://serverfault.com/questions/603987/whats-the-advantage-of-synchronizing-uid-gid-across-linux-machines)
- [How can I keep user accounts consistent across multiple machines?](https://unix.stackexchange.com/questions/141023/how-can-i-keep-user-acccounts-consistent-accross-multiple-machines)

</details>

<details>
<summary><b>成功地系统性能调整需遵循哪些原则? ***</b></summary><br>

待续.

参考文档:

- [An Introduction to Performance Tuning](https://www.oreilly.com/library/view/system-performance-tuning/059600284X/ch01.html)

</details>

<details>
<summary><b>简述在BSD系统中的启动配置文件和目录.</b></summary><br>

在BSD中,主要的启动配置文件是`/etc/defaults/rc.conf`.系统启动脚本文件(如`/etc/rc`和`/etc/rc.d`)只包括该文件.

如果要将其他程序添加为系统启动,则需要更改`/etc/rc.conf`文件而不是`/etc/defaults/rc.conf`.

</details>

<details>
<summary><b>CPU花费大量时间等待IO操作完成.哪个工具可以诊断是哪些进程在等待IO?如何最小化IO等待时间? ***</b></summary><br>

待续.

参考文档:

- [Can anyone explain precisely what IOWait is?](https://serverfault.com/questions/12679/can-anyone-explain-precisely-what-iowait-is)

</details>

<details>
<summary><b>初级工程师意外的损坏了生产数据库,如何防止这种情况?</b></summary><br>

**创建灾难恢复方案**

灾难恢复和业务连续性方案是一个组织中整体风险管理的重要部分,是用来恢复和保护业务IT基础设施的一系列文档化的操作过程.

如果没有恢复方案,那么恢复工作将变成重建工作,需要从头开始重新创建丢失的任何内容.

恢复方案需要使用常见的真实数据来模拟在灾难场景中备份该如何使用.

**创建灾难恢复中心**

如果主要设施的功能发生意外中断,那么服务和所有操作活动都会切换到备份中心,从而将服务的不可用性限制在一个很小的时间段内.

该备份中心设施是否有足够的带宽大小和功率来扩展和处理重大灾难期间增加的负载?资源是否足够用于定期测试故障转移?

**创建定期备份并测试!**

备份是保护数据资产的一种方式.当拥有多个数据副本时,如果其中一个数据副本被销毁也无关紧要(成本只有从备份中恢复丢失数据).

当数据丢失时,有一点是肯定的:宕机时间.

为了确保任何备份的可用性和完整性,必须定期进行恢复测试.理想情况下,在每次备份后就应该进行测试,以确保数据能成功恢复.不过,由于缺乏可用资源或时间限制,这通常是不实际的.

确保对全部虚拟机和重要的组件进行备份.

**创建快照:vm,disks或lvm**

如果想恢复服务器之前的状态,快照是一种完美的方法,但它只是一种"快速方法",系统更改太多后快照就无法恢复了.

始终在对生产环境进行更改之前创建它们.

磁盘快照用来生成整个磁盘的快照.这些快照不是用来恢复单个数据块(如丢失的用户帐户)的,虽然这是可以的.它的主要目的是在磁盘发生故障时恢复整个磁盘.

LVM快照主要用于将数据从生产环境轻松复制到演示环境.

请记住一点:快照不是备份!

**开发和测试环境**

生产环境是公司或客户使用的包括应用程序及其数据库的真实实例.生产数据库包含所有真实数据.

基于生产数据库来配置开发环境,而不是直接使用备份.这样工程师可以在开发和测试环境上操作,而只有部分人才能在更改批准后更新生产环境.

所有环境(如prod,dev和test)都应该有一个主要区别:服务的数据授权.例如,测试环境中的postgres数据库实例应尽可能与生产环境保持一致,但是,为了避免数据库名称和登录错误,登陆密码应该不同.

**单点故障**

避免单点故障的常见方法是为每个必需的资源提供冗余组件.如果其中一个组件发生故障,服务仍可继续运行.

**数据库的同步和复制过程**

复制过程非常脆弱,容易出错.

一个好主意是稍微延长的数据复制延迟(如:DRC).与副本一样,数据更改通常需要几分钟来复制,因此一旦发生数据丢失,丢失的数据不会出现在副本数据库中.

**创建用户,角色和权限的数据库模型,使用不同的保护方法**

只有非常高级的开发人员才具有数据库管理员权限,其他人真的不需要写权限来克隆数据库.另一方面,不要给开发人员生产环境的写权限.

生产数据库应该拒绝来自任何非生产环境的服务器和PC的连接,即使它提供了有效的用户名/密码.

**故障后创建摘要/总结文档**

总结文档受众包括客户,上级领导,同行,公司的管理团队以及投资者等.

根据时间线解释导致服务中断的原因.每个事故都是在特定时间被特定操作触发,从而导致一些意外行为.例如,服务器需要重新启动,我们希望它们完好无损地恢复,但这并没有发生.

此外,每个事故都有一个根本原因:重启本身是触发器,但驱动程序中的错误导致了实际中断.最后,每个事故都会产生影响,最明显的是该网站出现故障.

总结文档总结了最重要的问题:如何阻止中断发生.

尽管中断让人很痛苦,但你能做的最好的事情就是以清晰透明的方式正确地处理它,而不是忽略它.

**如果已犯下错误...**

  > "*Humans are just apes with bigger computers.*" - african_cheetah (Reddit)
  >
  > "*I've come to appreciate not having access to things I don't absolutely need.*" - warm_vanilla_sugar (Reddit)
  >
  > Document whatever happened somewhere. Write setup guides. Failure is instructive.

参考文档:

- [Accidentally destroyed production database on first day of a job...](https://www.reddit.com/r/cscareerquestions/comments/6ez8ag/accidentally_destroyed_production_database_on/)
- [Postmortem of database outage of January 31](https://about.gitlab.com/2017/02/10/postmortem-of-database-outage-of-january-31/)
- [How to write an Incident Report/Postmortem](https://sysadmincasts.com/episodes/20-how-to-write-an-incident-report-postmortem)

</details>

<details>
<summary><b>如何在不重启的情况下向Linux服务器中添加新磁盘?如何让LVM中重新扫描并添加它?</b></summary><br>

待续.

参考文档:

- [How to Add New Disk in Linux CentOS 7 Without Rebooting](https://linoxide.com/linux-how-to/add-new-disk-centos-7-without-rebooting/)

</details>

<details>
<summary><b>简析Linux进程管理中每个系统调用的作用.</b></summary><br>

以下为部分用来管理进程的系统调用：

- `Fork()`: 创建一个子进程
- `Exec()`: 执行一个新进程
- `Wait()`: 让进程进入等待状态
- `Exit()`: 让进程退出或终止
- `Getpid()`: 查找进程的唯一PID
- `Getppid()`: 查找进程的父进程PID
- `Nice()`: 修改当前运行的进程的优先级

参考文档:

- [System Calls](http://faculty.salina.k-state.edu/tim/ossg/Introduction/sys_calls.html)

</details>

<details>
<summary><b>为什么无法挂载根文件系统? ***</b></summary><br>

待续.

参考文档:

- [What does "mounting a root file system" mean exactly?](https://superuser.com/questions/193918/what-does-mounting-a-root-file-system-mean-exactly)
- [How does a kernel mount the root partition?](https://unix.stackexchange.com/questions/9944/how-does-a-kernel-mount-the-root-partition)

</details>

<details>
<summary><b>删除100G总量的文件的最好方法是什么? ***</b></summary><br>

待续.

参考文档:

- [Is there a way to delete 100GB file on Linux without thrashing IO/load?](https://serverfault.com/questions/336917/is-there-a-way-to-delete-100gb-file-on-linux-without-thrashing-io-load)
- [rm on a directory with millions of files](https://serverfault.com/questions/183821/rm-on-a-directory-with-millions-of-files)

</details>

<details>
<summary><b>简析Linux中的中断和中断处理程序.</b></summary><br>

**中断**:是指CPU对I/O设备发来的中断信号的一种响应.CPU保护并暂停当前进程,转而去处理引发中断的进程.执行完后,再返回到原进程继续执行.I/O设备可以是字符设备(键盘),块设备(磁盘)或通信设备(网络)等.由于中断是外部造成的,所以又叫外中断.

**陷入**:陷入是由CPU进程内部事件引发的中断,因此叫陷入或内中断.其产生的原因往往是由于进程本身在运行时出现了异常.

中断又可分为屏蔽中断和非屏蔽中断两类.可由程序控制其屏蔽的中断称为屏蔽中断或可屏蔽中断.屏蔽时,CPU将不接受中断.反之,不能由程序控制其屏蔽,CPU一定要立即处理的中断称为非屏蔽中断或不可屏蔽中断.而处理该中断过程的组件就叫**中断处理程序**.

**中断处理程序**通过与触发中断的外设进行通信来发送或接收数据.当中断处理程序执行完成时,它会执行一个特殊的从中断返回指令,恢复保存的寄存器并将中断屏蔽.

中断处理程序必须快速运行,因为它阻止任何其他中断运行.在Linux内核中,中断处理分为两部分:

- "上半部分"完成尽可能少的比较紧急的功能,它往往只是简单地读取寄存器中的中断状态并清除中断标志后进行"登记中断"的工作.
- "下半部分"作为工作重心,完成中断事件的绝大多数任务.如将数据复制到进程存储器,更新内核数据结构等.

参考文档:

- [How is an Interrupt handled in Linux? (original)](https://unix.stackexchange.com/questions/5788/how-is-an-interrupt-handled-in-linux)
- [Interrupts and Interrupt Handlers](https://notes.shichao.io/lkd/ch7/)

</details>

<details>
<summary><b>设计高可用性应用程序时在架构级别和应用程序级别分别需要考虑哪些因素? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>inode中存储了哪些字段?</b></summary><br>

在POSIX系统中,文件具有以下属性,可由stat系统调用查询:

- **Device ID**:标识了包含文件的设备.
文件序列号
- **file mode**:确定文件类型以及文件属主,属组和其他人如何访问该文件.
- **link count**:文件的硬链接数. 
- **User ID**:文件属主的ID.
- **Group ID**:文件属组的ID.
- **device ID**:如果是设备文件则显示设备ID.
- **size of the file**:文件大小,以字节数表示.
- **Timestamps**:显示上次修改inode本身的时间(ctime,inode更改时间),上次修改的文件内容(mtime,修改时间)的时间和最后一次访问(atime,访问时间)文件的时间.
- **I/O block size**:首选的block类型.
- **number of blocks**:文件的block数.

参考文档:

- [Inodes - an Introduction](http://www.grymoire.com/Unix/Inodes.html)

</details>

<details>
<summary><b>普通用户可以查看<code>/etc/passwd</code>.这是安全漏洞吗?还有其他遮盖密码的方案吗?</b></summary><br>

在大多数Linux系统上,hash后的密码(_hashed passwords_)都存储在`/etc/shadow`中:

```bash
-rw-r----- 1 root shadow 1349 2016-07-03 03:54 /etc/shadow
```

在BSD系统上则存储在`/etc/master.passwd`中.

执行认证的程序仍需要以`root`权限运行:

```bash
-rwsr-xr-x 1 root root 42792 2016-02-14 14:13 /usr/bin/passwd
```

如果你不喜欢`setuid root`程序和一个包含系统上所有hash后的密码的单个文件,则可以将其替换为**Openwall TCB PAM module**.这为每个用户提供了自己的文件来存储他们的hash后的密码 - 从而使得系统上的`setuid root`程序的数量大大减少.

参考文档:

- [Ordinary users are able to read /etc/passwd, is this a security hole? (original)](https://serverfault.com/questions/286654/ordinary-users-are-able-to-read-etc-passwd-is-this-a-security-hole/286657#286657)
- [tcb - the alternative to /etc/shadow](https://www.openwall.com/tcb/)
- [Why shadow your passwd file?](https://www.tldp.org/HOWTO/Shadow-Password-HOWTO-2.html)

</details>

<details>
<summary><b>使用systemd来替代SysV init的好处是什么? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>如何在文件修改后立即执行命令?</b></summary><br>

如下:

```bash
while inotifywait -e close_write filename ; do

  echo "changed" >> /var/log/changed

done
```

</details>

<details>
<summary><b>需要复制大量数据.简述最高效的方法 ***</b></summary><br>

待续.

参考文档:

- [Copying a large directory tree locally? cp or rsync?](https://serverfault.com/questions/43014/copying-a-large-directory-tree-locally-cp-or-rsync)

</details>

<details>
<summary><b>简述使用LVM的风险.</b></summary><br>

**使用LVM的风险**

- 使用SSD或VM hypervisor时容易产生写入缓存问题
- 由于更复杂的磁盘结构,恢复数据变得更难了
- 更难以正确调整文件系统的大小
- 快照难以使用,速度慢且有缺陷
- 鉴于以上的问题,需要一些技巧才能正确配置使用

参考文档:

- [LVM dangers and caveats (original)](https://serverfault.com/questions/279571/lvm-dangers-and-caveats)

</details>

<details>
<summary><b>Python开发团队对选择uwsgi还是gunicorn很困扰.从系统管理员的角度来看两者的优缺点是什么? ***</b></summary><br>

待续.

参考文档:

- [uWSGI vs. Gunicorn, or How to Make Python Go Faster than Node](https://blog.kgriffs.com/2012/12/18/uwsgi-vs-gunicorn-vs-node-benchmarks.html)

</details>

<details>
<summary><b>如果<code>kill -9</code>不起作用怎么办?描述使用SIGKILL失败的例外情况.</b></summary><br>

只要你有杀死进程的权限,`kill -9`(`SIGKILL`)通常都是有效的,比如说你启动了该进程而不是setuid/setgid,或你是root.有个例外是:即使是root也无法向PID 1(init进程)发送终止信号.

但`kill -9`不能确保立即生效.所有信号,包括`SIGKILL`,都是异步传递的:内核需要花时间来传递它们.通常,传递信号最多需要几微秒.但是,如果目标已阻塞了信号,则信号将排队直到目标解除阻塞.

进程通常不能阻止`SIGKILL`,但是内核代码可以,而进程可以在处理系统调用时执行内核代码.

在系统调用时被阻塞的进程处于不可中断的睡眠状态,`ps`或`top`命令将(在大多数unices上)将其显示为状态**D**.

由于**D**状态进程是不可中断的只有重启机器才能删除它,不然系统将不会自动处理.

通常情况下,进程很少有机会长期处于**D**状态.如果确实如此,那么表示系统中有一些未正确处理的事情.这也可能是一个潜在的错误.

一个经典的长期不可中断的睡眠状态案例是当进程通过NFS访问没有响应的服务器的文件.现在会尽量避免出现不间断睡眠状态(例如,在Linux下,mount选项允许信号中断NFS文件访问).

有时可能会在`ps`或`top`输出中看到标记为**Z**的进程,这就是僵尸进程.当子进程比父进程先结束,而父进程又没有回收子进程,释放子进程占用的资源,此时子进程就成为了一个僵尸进程.如果父进程先退出,子进程会被init接管,init成为它的父进程.子进程退出后init会回收其占用的相关资源.

总结:

- 僵尸进程无法被杀死,因为它们已经死亡并等待其父进程回收它们
- 处于阻塞状态的进程在它们再次唤醒之前不会死亡
- init进程很特殊:它不会获得它不想处理的信号,因此它可以忽略**SIGKILL**
- 即使发送了**SIGKILL**信号,处于不可中断的睡眠状态的进程也可能无法被终止并释放其资源.这是可能需要重新启动Unix系统以解决临时软件问题的少数情况之一

参考文档:

- [What if kill -9 does not work? (original)](https://unix.stackexchange.com/questions/5642/what-if-kill-9-does-not-work)
- [How to kill a process in Linux if kill -9 has no effect](https://serverfault.com/questions/458261/how-to-kill-a-process-in-linux-if-kill-9-has-no-effect)
- [When should I not kill -9 a process?](https://unix.stackexchange.com/questions/8916/when-should-i-not-kill-9-a-process)
- [SIGTERM vs. SIGKILL](https://major.io/2010/03/18/sigterm-vs-sigkill/)

</details>

<details>
<summary><b><code>nohup</code>,<code>disown</code>和<code>&</code>有什么区别.同时使用会发生什么?</b></summary><br>

- `&`仅仅是将作业放在后台运行,但仍会在前台输出信息.
- `disown`将程序从shell的作业控制中移除,但仍然和终端相连.这样shell就不会发送**SIGHUP**信号给它.显然,它只能用于后台作业,因为当有前台作业在运行时就无法切入它了.
- `nohup`将进程与终端断开连接,将其输出重定向到`nohup.out`同时屏蔽**SIGHUP**信号.这样该进程就不会收到任何已发送的**SIGHUP**信号.它完全独立于作业控制,理论上也可用于前台作业(虽然不是很有用).

如果将所有三个一起使用,则进程将在后台运行,并从shell的作业控制中移除,且与终端断开连接.

参考文档:


- [Difference between nohup, disown and & (original)](https://unix.stackexchange.com/questions/3886/difference-between-nohup-disown-and)

</details>

<details>
<summary><b>使用<code>chroot</code>的优点是什么?何时以及为何使用它?在chroot环境中挂载dev,proc,sys的目的是什么?</b></summary><br>

chroot环境的优点之一是生成一个与原系统隔离的系统目录结构.`chroot`可以在原文件系统中分隔出一个单独的文件系统,区别是新文件系统使用新创建的根(/)作为其根目录.

chroot jail是一种将进程及其子进程与系统其他部隔离开来的方法.它不适用与以root身份运行的进程,因为root用户可以非常容易地突破这项限制.

具体使用方法是创建一个目录树,并在其中复制或链接程序运行所需的所有系统文件.然后使用`chroot()`系统调用将根目录更改为新目录树的根目录,最后在该chroot环境中启动程序.由于该程序不能引用修改后的根目录之外的路径,因此它无法在新目录树外执行恶意(读/写等)操作.

在Linux上,使用挂载目录是实现chroot根目录的好办法.使用挂载可以同时引入多个目录.比如直接挂载你想限制的目录作为目录树就可以了.

Chroot环境的用处:

- 重装bootloader
- 重置登录密码
- 执行内核升级或降级
- 重建initramdisk
- 修复 **/etc/fstab**
- 使用包管理器重新安装包
- 其他

在chroot环境中工作时,需要挂载一些特殊的文件系统以便所有程序都能正常运行.如`/dev`,`/sys`和`/proc`,许多任务都需要它们.

参考文档:

- [Its all about Chroot](https://medium.com/@itseranga/chroot-316dc3c89584)
- [Best Practices for UNIX chroot() Operations](http://www.unixwiz.net/techtips/chroot-practices.html)
- [Is there an easier way to chroot than bind-mounting?](https://askubuntu.com/questions/32418/is-there-an-easier-way-to-chroot-than-bind-mounting)
- [What's the proper way to prepare chroot to recover a broken Linux installation?](https://superuser.com/questions/111152/whats-the-proper-way-to-prepare-chroot-to-recover-a-broken-linux-installation)

</details>

<details>
<summary><b>什么是段错误(segfaults)?如何识别产生该错误的原因?</b></summary><br>

**段错误**(又名_segfault_)是导致程序崩溃的常见原因.Segfaults是由程序试图读取或写入非法的内存位置引起的.

程序内存可以分为不同的段:

- 程序指令的文本段
- 在编译时定义变量和数组的数据段
- 指令和函数中定义临时(或自动)变量的堆栈段
- 运行时由函数分配的变量的堆段,例如`malloc`(在C中)

在实践中,段错误几乎都是由于尝试读取或写入不存在的数组元素产生,如使用指针之前未正确定义,或者(在C程序中)意外使用变量的值作为地址.因此,当进程A读取内存位置0x877时,它读取的是驻留在RAM中的其他物理位置的信息,而不是进程B读取0x877时的信息.

所有现代操作系统都支持和使用分段,因此所有操作系统都会产生段错误.

在以下情况下也可能发生段错误:

- 一个有缺陷的程序/命令,只能通过补丁来修复
- 在C编程中尝试访问数组末尾之外的数组时也会出现
- 在chroot环境中,当缺少关键的共享库,配置文件或`/dev/`时也会出现
- 有时硬件或内存故障或驱动程序也会产生问题
- 计算机物理设备的环境过热也会产生此问题

要调试此类错误,请尝试以下一种或所有技术:

- 启用核心文件:`$ ulimit -c unlimited`
- 重现崩溃:`$ ./<program>`
- 使用gdb调试崩溃:`$ gdb <program> [core file]`
- 或者运行`LD_PRELOAD=...path-to.../libSegFault.so <program>`来获取backtrace和加载的库等信息

同时:

- 确保正确安装和配置了硬件
- 始终应用所有补丁并使用最新的系统
- 确保在chroot环境中安装所有依赖项
- 为Apache等受支持的服务启用核心dump
- 使用`strace`,这是一个有用的诊断,指导和调试工具

有时段错误不是由于程序中的错误而是由于系统内存限制设置得太低引起的.通常,堆栈大小的限制会导致这种问题(堆栈溢出).请在bash中使用`ulimit`命令来检查内存限制.

参考文档:

- [What are segmentation faults (segfaults), and how can I identify what's causing them? (original)](https://kb.iu.edu/d/aqsj)
- [What is a segmentation fault on Linux?](https://stackoverflow.com/questions/3200526/what-is-a-segmentation-fault-on-linux)
- [Segmentation fault when calling a recursive bash function](https://unix.stackexchange.com/questions/296641/segmentation-fault-when-calling-a-recursive-bash-function)
- [Troubleshooting Segmentation Violations/Faults](http://web.mit.edu/10.001/Web/Tips/tips_on_segmentation.html)
- [Can one use libSegFault.so to get backtraces for SIGABRT?](https://stackoverflow.com/questions/18706496/can-one-use-libsegfault-so-to-get-backtraces-for-sigabrt)

</details>

<details>
<summary><b>某个进程运行缓慢.使用哪些工具可以检查其运行了多长时间?</b></summary><br>

待续.

参考文档:

- [How to check how long a process has been running?](https://unix.stackexchange.com/questions/7870/how-to-check-how-long-a-process-has-been-running)
- [Linux how long a process has been running?](https://www.cyberciti.biz/faq/how-to-check-how-long-a-process-has-been-running/)
- [How to see system call that executed in current time by process?](https://stackoverflow.com/questions/42677724/how-to-see-system-call-that-executed-in-current-time-by-process)

</details>

<details>
<summary><b>Linux中的文件描述符是什么?</b></summary><br>

在Unix和相关的操作系统中,文件描述符(FD)是用于访问文件或其他输入/输出资源的抽象指示符(句柄),就像是管道或网络套接字.文件描述符是构成POSIX应用程序编程接口的一部分.

</details>

<details>
<summary><b>哪种方式可以增加随机熵池来生成随机密码?如何改进?</b></summary><br>

建议使用`/dev/urandom`,而不是`/dev/random`.`/dev/random`和`/dev/urandom`之间的区别是:

- 在信息理论的安全的算法中,`/dev/random`在理论上可能更好.这种算法可以抵御目前以及以后的技术.

- `/dev/urandom`不会封锁,而`/dev/random`可能会封锁.`/dev/random`依赖于系统中断产生的熵池,因此在系统的中断数不足时,`/dev/urandom`会一直封锁,尝试读取的进程就会进入等待状态,直到系统的中断数充分够用.`/dev/urandom`可以保证数据的随机性.`/dev/urandom`不依赖系统的中断,也就不会造成进程等待,但是数据的随机性也不高.二者都是伪随机.

所以使用`/dev/urandom`就不用担心熵池的问题.

`/dev/urandom`永远不会封锁,且`/dev/urandom`是安全的,只要它自上次启动后已经收到足够(32个随机字节)的"初始熵"字节.大多数Linux在安装时会创建随机种子(来自`/dev/random`)并将其保存在磁盘上.每次重新启动时,将读取种子并将其送入`/dev/urandom`来立即生成一个新种子(来自`/dev/urandom`)替换原有种子.从而保证了`/dev/urandom`将始终具有足够的初始熵来用于任何普通的加密工作,如生成密码.

所有守护进程都需要随机值,当所有可用熵都已耗尽,它们就会暂停并等待,从而导致应用程序的过度延迟.更糟糕的是,由于目前大多数应用程序要么使用在程序初始化时创建的随机种子,要么使用`/dev/urandom`来避免阻塞,因此应用程序会受到质量较低的随机数据的影响,这可能会影响数据通信安全,并增加对隐私数据进行解密分析的机会.

确认当前可用的熵字节数,使用:

```bash
cat /proc/sys/kernel/random/entropy_avail
```

**rng-tools**

Fedora/Rh/Centos: `sudo yum install rng-tools`.

Deb: `sudo apt-get install rng-tools`.

在生成密钥前执行`sudo rngd -r /dev/urandom`.

**haveged**

Fedora/Rh/Centos: `sudo yum install haveged`并增加`/usr/local/sbin/haveged -w 1024`到`/etc/rc.local`.

Deb: `sudo apt-get install haveged`并增加`DAEMON_ARGS="-w 1024"`到`/etc/default/haveged`.

在生成密钥前执行`sudo rngd -r /dev/urandom`.

参考文档:

- [Feeding /dev/random entropy pool? (original)](https://security.stackexchange.com/questions/89/feeding-dev-random-entropy-pool)
- [GPG does not have enough entropy](https://serverfault.com/questions/214605/gpg-does-not-have-enough-entropy)

</details>

<details>
<summary><b><code>/sbin/nologin</code>,<code>/bin/false</code>和<code>/bin/true</code>的区别是什么?</b></summary><br>

将用户的shell设置为`/sbin/nologin`时,当该用户登录,会收到一条礼貌消息,指出"此帐户当前不可用".

`/bin/false`用户在登录时什么也不做只是返回一个错误状态,然后立即退出,并且不会有任何提示.

`/bin/nologin`是一个对用户更加友好的选项,可以向试图登录的用户提供可自定义的消息.但是nologin和false都会产生相同的最终结果,即用户无法通过ssh登录shell.

参考文档:

- [What's the difference between /sbin/nologin and /bin/false](https://unix.stackexchange.com/questions/10852/whats-the-difference-between-sbin-nologin-and-bin-false)
- [Why do some system users have /usr/bin/false as their shell?](https://superuser.com/questions/1183311/why-do-some-system-users-have-usr-bin-false-as-their-shell)

</details>

<details>
<summary><b>磁盘瓶颈可以会出现什么征兆? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>在FreeBSD中报错<code>maxproc limit exceeded by uid %i ...</code>意味着什么?</b></summary><br>

FreeBSD的内核只允许在一定时间内存在一定数量的进程.该数量基于**kern.maxusers**变量.

**kern.maxusers**也会影响各种其他内核限制,如网络缓冲区.如果机器负载很高,请增加**kern.maxusers**值,除了最大进程数之外,也会增加其他的系统限制.

要调整**kern.maxusers**值,请参阅手册的文件/进程限制部分.虽然该部分涉及打开文件数,但相同适用于进程限制.

如果机器负载很低但运行了大量进程,请在`/boot/loader.conf`中调整**kern.maxproc**参数.

</details>

<details>
<summary><b>如何逐行读取文件并将值赋给变量?</b></summary><br>

如下:

```bash
while IFS='' read -r line || [[ -n "$line" ]] ; do
  echo "Text read from file: $line"
done < "/path/to/filename"
```

解析:

- `IFS=''` (或`IFS=`)防止首尾有空格.
- `-r`防止启用反斜杠转义.
- `|| [[ -n $line ]]`防止最后一行如果不以`\ n`结尾时被忽略(因为当遇到EOF时,read会返回非零退出代码).

参考文档:

- [Read a file line by line assigning the value to a variable](https://stackoverflow.com/questions/10929453/read-a-file-line-by-line-assigning-the-value-to-a-variable)

</details>

<details>
<summary><b>客户报告在ssllabs扫描中只得到了B级,请准备ssl配置的最佳实践列表. ***</b></summary><br>

参考文档:

- [Getting a Perfect SSL Labs Score](https://michael.lustfield.net/nginx/getting-a-perfect-ssl-labs-score)
- [17 small suggestions how to improve ssllabs.com/ssltest/](https://community.qualys.com/thread/14023)
- [How do you score A+ with 100 on all categories on SSL Labs test with Let's Encrypt and Nginx?](https://stackoverflow.com/questions/41930060/how-do-you-score-a-with-100-on-all-categories-on-ssl-labs-test-with-lets-encry)

</details>

<details>
<summary><b>CPU jumps意味着什么?</b></summary><br>

操作系统是非常繁忙的,特别是当你让它做某事时(即使你没有),所以当我们看到一个活跃的生产环境时,总会发生一些事情.

大多数此类活动都有"突发性",意味着在短暂的时间内有大量进程激烈活动.比如任何类型的基于网络的活动(如处理PHP请求),或者OS维护(如文件系统维护,页面回收,磁盘I/O请求).

如果经常遇到这样的有很多突发进程的情况,那么表示CPU使用处于不正常状态中.

正如"500-内部服务器错误"所示,大量的上下文切换会使情况变得更糟.

参考文档:

- [What does "CPU jumps” mean? (original)](https://stackoverflow.com/questions/32185607/what-does-cpu-jumps-mean)

</details>

<details>
<summary><b>如何在Linux中跟踪系统调用?简述几种可行的方法.</b></summary><br>

**SystemTap**

这是最强大的方法.它甚至可以显示调用参数:

使用方法:

```bash
sudo apt-get install systemtap
sudo stap -e 'probe syscall.mkdir { printf("%s[%d] -> %s(%s)\n", execname(), pid(), name, argstr) }'
```

在别的终端使用:

```bash
sudo rm -rf /tmp/a /tmp/b
mkdir /tmp/a
mkdir /tmp/b
```

简单输出:

```bash
mkdir[4590] -> mkdir("/tmp/a", 0777)
mkdir[4593] -> mkdir("/tmp/b", 0777)
```

**`strace`使用`-f|-ff`参数**

可以使用`-f`和`-ff`选项.如下:

```bash
strace -f -e trace=process bash -c 'ls;'
```

- `-f` :跟踪当前进程及其通过fork系统调用所创建的子进程.

- `-ff` :常与-o选项联合使用,可以把每个进程(子进程)的跟踪结果分别输出到相应的filename.pid文件中,pid是各个进程ID.与`-c`不兼容,因为每个进程计数不会被保留.

**`ltrace -S`显示系统调用和库调用**

这个非常棒的工具可以进一步了解程序执行时在做什么.

**`ftrace`最简单的可运行例子**

这是一个最简单的可运行的例子.用`sudo`运行:

```bash
#!/bin/sh
set -eux

d=debug/tracing

mkdir -p debug
if ! mountpoint -q debug; then
  mount -t debugfs nodev debug
fi

# Stop tracing.
echo 0 > "${d}/tracing_on"

# Clear previous traces.
echo > "${d}/trace"

# Find the tracer name.
cat "${d}/available_tracers"

# Disable tracing functions, show only system call events.
echo nop > "${d}/current_tracer"

# Find the event name with.
grep mkdir "${d}/available_events"

# Enable tracing mkdir.
# Both statements below seem to do the exact same thing,
# just with different interfaces.
# https://www.kernel.org/doc/html/v4.18/trace/events.html
echo sys_enter_mkdir > "${d}/set_event"
# echo 1 > "${d}/events/syscalls/sys_enter_mkdir/enable"

# Start tracing.
echo 1 > "${d}/tracing_on"

# Generate two mkdir calls by two different processes.
rm -rf /tmp/a /tmp/b
mkdir /tmp/a
mkdir /tmp/b

# View the trace.
cat "${d}/trace"

# Stop tracing.
echo 0 > "${d}/tracing_on"

umount debug
```

简单输出:

```bash
# tracer: nop
#
#                              _-----=> irqs-off https://sourceware.org/systemtap/documentation.html
#                             / _----=> need-resched
#                            | / _---=> hardirq/softirq
#                            || / _--=> preempt-depth
#                            ||| /     delay
#           TASK-PID   CPU#  ||||    TIMESTAMP  FUNCTION
#              | |       |   ||||       |         |
            mkdir-5619  [005] .... 10249.262531: sys_mkdir(pathname: 7fff93cbfcb0, mode: 1ff)
            mkdir-5620  [003] .... 10249.264613: sys_mkdir(pathname: 7ffcdc91ecb0, mode: 1ff)
```

这个方法很厉害的一面是它可以一次显示系统上所有进程的函数调用,当然也可以使用`set_ftrace_pid`来过滤感兴趣的PID.

参考文档:

- [How do I trace a system call in Linux? (original)](https://stackoverflow.com/questions/29840213/how-do-i-trace-a-system-call-in-linux)
- [Does ftrace allow capture of system call arguments to the Linux kernel, or only function names?](https://stackoverflow.com/questions/27608752/does-ftrace-allow-capture-of-system-call-arguments-to-the-linux-kernel-or-only)
- [How to trace just system call events with ftrace without showing any other functions in the Linux kernel?](https://stackoverflow.com/questions/52764544/how-to-trace-just-system-call-events-with-ftrace-without-showing-any-other-funct)
- [What system call is used to load libraries in Linux?](https://unix.stackexchange.com/questions/226524/what-system-call-is-used-to-load-libraries-in-linux)

</details>

<details>
<summary><b>如何删除目录中某些文件以外的所有文件?</b></summary><br>

1.使用`extglob`:

```bash
shopt -s extglob
rm !(textfile.txt|backup.tar.gz|script.php|database.sql|info.txt)
```

2.使用`find`:

```bash
find . -type f -not -name '*txt' -print0 | xargs -0 rm --
```

</details>

<details>
<summary><b>如何在Bash中检查字符串是否包含子字符串?</b></summary><br>

如果使用双括号,也可以在case语句之外使用`*`(通配符):

```bash
string='some text'
if [[ $string = *"My long"* ]] ; then
  true
fi
```

</details>

<details>
<summary><b>简介<code>2>&-</code>,<code>2>/dev/null</code>,<code>|&</code>,<code>&>/dev/null</code>和<code>>/dev/null 2>&1</code>之间的区别.</b></summary><br>

- **数字1** = 标准输出 (如`STDOUT`)
- **数字2** = 标准错误 (如`STDERR`)
- 如果未明确给出数字,那么shell(bash)将默认为**数字1**

让我们一个个来介绍:

`2>&-`

常用形式是`M>&-`,其中**M**是一个文件描述符.这将关闭所引用的文件描述符**M**的输出.

`2>/dev/null`

常用形式是`M>/dev/null`,其中**M**是一个文件描述符.这将把文件描述符**M**的输出重定向到`/dev/null`.

`2>&1`

常用形式是`M>&N`,其中**M**和**N**是一个文件描述符.它将文件描述符**M**和**N**的输出组合成单个流.

`|&`

这是`2>&1 |`的缩写.它添加于Bash 4版本.

`&>/dev/null`

这是`>/dev/null 2>&1`的缩写.这将文件描述符2(`STDERR`)文件描述符1(`STDOUT`)的输出重定向到`/dev/null`.

`>/dev/null`

这是`1>/dev/null`的缩写.这将文件描述符1(`STDOUT`)的输出重定向到`/dev/null`.

参考文档:

- [Difference between 2>&-, 2>/dev/null, |&, &>/dev/null and >/dev/null 2>&1](https://unix.stackexchange.com/questions/70963/difference-between-2-2-dev-null-dev-null-and-dev-null-21)
- [Chapter 20. I/O Redirection](http://www.tldp.org/LDP/abs/html/io-redirection.html)

</details>

<details>
<summary><b>如何将stderr和stdout重定向到同一行命令中的不同文件?</b></summary><br>

只需将它们添加到一行`command 2 >> error 1 >> output`中.

但请注意,如果文件已有数据,则需要添加`>>`.`>`将覆盖文件中的任何现有数据.

所以如果不想追加的话,请执行`command 2> error 1> output`.

为了方便起见,也可以将`1>`写为`>`,因为默认文件描述符即是标准输出,所以`1>`和`>`是一回事.

因此`command 2> error 1> output`可缩写为`command 2> error > output`.

</details>

<details>
<summary><b>在一台24核的服务器上负载平均值大于30,但CPU显示有70%的空闲.这种情况的常见原因是什么?如何调试和修复?</b></summary><br>

如果cpu(s)需要在磁盘上等待读取或写入数据,那么处理涉及磁盘I/O的请求会非常慢.I/O Wait,表示CPU在等待磁盘上花费的时间的百分比.

让我们尝试如何使用一些终端命令行工具(`top`,`atop`和`iotop`)来确认磁盘I/O是否会降低应用程序性能.

调试示例:

- 确认I/O是否导致系统运行缓慢
- 查找正在被写入的磁盘
- 查找引起高I/O的进程
- 列出进程**状态**表
- 查找写入过多的文件
- 是否看到复制进程处于**D**状态来等待I/O工作由pdflush完成?
- 是否在磁盘上看到了大量的同步写入活动?

同时:

- 使用`top`命令 - 查看负载平均值和wa(等待时间)
- 使用`atop`命令监视DSK(磁盘)I/O统计信息
- 使用`iotop`命令实时查看磁盘读/写情况

改善性能的方法：

- 检查驱动器阵列配置
- 检查磁盘队列算法并调整
- 调整通用块的I/O参数
- 调整虚拟内存管理以提高I/O性能
- 检查和调整挂载选项和文件系统参数(也负责缓存)

参考文档:

- [发现并解决linux高I/O Wait问题 – 如何发现linux中引起高io等待的进程](http://coolnull.com/4444.html)
- [Linux server performance: Is disk I/O slowing your application? (original)](https://haydenjames.io/linux-server-performance-disk-io-slowing-application/)
- [Troubleshooting High I/O Wait in Linux](https://bencane.com/2012/08/06/troubleshooting-high-io-wait-in-linux/)
- [Debugging Linux I/O latency](https://superuser.com/questions/396696/debugging-linux-i-o-latency)
- [How do pdflush, kjournald, swapd, etc interoperate?](https://unix.stackexchange.com/questions/76970/how-do-pdflush-kjournald-swapd-etc-interoperate)
- [5 ways to improve HDD speed on Linux](https://thecodeartist.blogspot.com/2012/06/improving-hdd-performance-linux.html)

</details>

<details>
<summary><b>如何在SSH中强制使用认证方法?</b></summary><br>

强制密码登录:

```bash
ssh -o PreferredAuthentications=password -o PubkeyAuthentication=no user@remote_host
```

强制密钥登录:

```bash
ssh -o PreferredAuthentications=publickey -o PubkeyAuthentication=yes -i id_rsa user@remote_host
```

参考文档:

- [How to force ssh client to use only password auth?](https://unix.stackexchange.com/questions/15138/how-to-force-ssh-client-to-use-only-password-auth)

</details>

<details>
<summary><b>Postgres报错<code>Too many Open files</code>.如何解决?</b></summary><br>

可以通过减少`max_files_per_process`来解决这个问题.例如默认值为1000,将其减小为200.此参数位于`postgresql.conf`文件中,它用来设置服务器子进程能同时打开的最大文件数.

通常会编辑`/etc/security/limits.conf`文件,但这个文件只适用于通过PAM系统登录的用户.

</details>

<details>
<summary><b>在什么情况下,<code>df</code>和<code>du</code>在可用磁盘空间上结果不同?如何解决?</b></summary><br>

`du`检查的是目录的使用情况,但`df`检查的是空闲的inode.文件保持打开状态时在删除后仍会占用空间.

**解决方案1**

检查位于挂载点下的文件.通常,如果将目录(如sambafs)挂载到已有一个或多个文件的文件系统上时,这些文件无法查看但仍然占用磁盘空间.

**解决方案2**

另一方面,`df -h`和`du -sh`显示的硬盘大小不符是由于如Apache(httpd)将从磁盘中删除的大型日志文件保存在内存中.

可以通过运行`lsof | grep "/var" | grep deleted`来查看,其中`/var`是需要清理的目录.

输出显示如下:

```
httpd 32617 nobody 106w REG 9,4 1835222944 688166 /var/log/apache/awstats_log(deleted)
```

然后通过重新启动Apache(`service httpd restart`)来清除已删除文件上的锁,从而清除磁盘空间.

参考文档:

- [Why du and df display different values in Linux and Unix](https://linuxshellaccount.blogspot.com/2008/12/why-du-and-df-display-different-values.html)

</details>

<details>
<summary><b>加密和哈希有什么区别?</b></summary><br>

**哈希**:哈希是一种加密安全形式,它与**加密**不同,**加密**是首先加密消息然后解密的两步过程.**哈希**简化了解密,直接将消息转换为不可逆的固定长度的值或散列.

</details>

<details>
<summary><b>是否应该将根证书放在服务器上?</b></summary><br>

**自签名根证书**不需要/不应该配置在web服务器中.它们没有任何用处(客户端总是会忽略它们)并且由于其会增加SSL握手的大小从而导致轻微的性能(延迟)损失.

如果客户端在其信任库中没有根证书,那么它将不信任该网站,并且无法解决该问题.让web服务器发送根证书将无济于事 - 根证书必须来自受信任的第三方(在大多数情况下是浏览器供应商).

参考文档:

Useful resources:

- [SSL root certificate optional?](https://security.stackexchange.com/questions/65332/ssl-root-certificate-optional)

</details>

<details>
<summary><b>如何记录生产环境上所有root执行过的命令?</b></summary><br>

使用`auditd`工具:

1. 在`/etc/audit/audit.rules`中增加以下2行:

```bash
-a exit,always -F arch=b64 -F euid=0 -S execve
-a exit,always -F arch=b32 -F euid=0 -S execve
```

这将跟踪所有由root运行的命令(euid=0).为什么要两个规则?execve系统调用必须同时追踪32位和64位代码.

2. 为了避免日志记录`auid=4294967295`信息,将`audit=1`加到内核的命令行中(通过编辑`/etc/default/grub`).

3. 将以下这行

```bash
session  required                pam_loginuid.so
```

加到所有与登录相关的PAM配置文件中(`/etc/pam.d/{login,kdm,sshd}`),但不要加在与su或sudo相关的文件中.这将允许auditd在调用sudo或su时能正确获取用户的uid.

重启系统.

登录并执行一些命令:

```bash
$ id -u
1000
$ sudo ls /
bin  boot  data  dev  etc  home  initrd.img  initrd.img.old  lib  lib32  lib64  lost+found  media  mnt  opt  proc  root  run  sbin  scratch  seLinux  srv  sys  tmp  usr  var  vmlinuz  vmlinuz.old
$ sudo su -
# ls /etc
[...]
```

查看`/var/log/audit/auditd.log`文件.

参考文档:

- [Log all commands run by admins on production servers](https://serverfault.com/questions/470755/log-all-commands-run-by-admins-on-production-servers)

</details>

<details>
<summary><b>如何防止<code>dd</code>冻结系统?</b></summary><br>

尝试使用ionice:

```bash
ionice -c3 dd if=/dev/zero of=z
```

这将以IO"空闲"为优先级来启动`dd`进程:只有在某段时间内没有其他进程使用磁盘IO时才获得磁盘使用权.

不过,当系统将缓存写入磁盘时,仍然会使缓存泛滥并导致冻结.调整`/proc/sys/vm/`下尤其是`dirty_*`的参数可以缓解这个情况.

</details>

<details>
<summary><b>如何将进程限制为不超过CPU占用率的X%?</b></summary><br>

**nice/renice**

nice可以对系统进行"一次性"调整,它可以修改进程的优先级,让进程运行得不那么频繁.这个功能在运行cpu密集型的后台进程或批处理作业时尤为有用

```bash
nice COMMAND
```

**cpulimit**

cpulimit命令的工作原理是为进程预设一个cpu占用率上限,并实时监控进程是否超出此限制,若超出则让该进程暂停运行一段时间.cpulimit的优势是可以控制进程的cpu使用率的上限值,但与nice相比也有缺点,那就是即使cpu是空闲的,进程也不能完全使用整个cpu资源.

```bash
cpulimit -l 50 COMMAND
```

**cgroups**

cgroups可以限制一组进程,而不是单独一个:

```bash
cgcreate -g cpu:/cpulimited
cgset -r cpu.shares=512 cpulimited
cgexec -g cpu:cpulimited COMMAND_1
cgexec -g cpu:cpulimited COMMAND_2
cgexec -g cpu:cpulimited COMMAND_3
```

</details>

<details>
<summary><b>如何挂载临时ram分区?</b></summary><br>

```bash
# -t - filesystem type
# -o - mount options
mount -t tmpfs tmpfs /mnt -o size=64M
```

</details>

<details>
<summary><b>如何杀死锁定文件的进程?</b></summary><br>

```bash
fuser -k filename
```

</details>

<details>
<summary><b>其他管理员在调试服务器时意外输入:<code>chmod -x /bin/chmod</code>.如何重置权限?</b></summary><br>

```bash
# 1:
cp /bin/ls chmod.01
cp /bin/chmod chmod.01
./chmod.01 700 file

# 2:
/bin/busybox chmod 0700 /bin/chmod

# 3:
setfacl --set u::rwx,g::---,o::--- /bin/chmod

# 4:
/usr/lib/ld*.so /bin/chmod 0700 /bin/chmod
```

参考文档:

- [What can you do when you can't chmod chmod?](https://www.networkworld.com/article/3002286/operating-systems/what-can-you-do-when-you-cant-chmod-chmod.html)

</details>

<details>
<summary><b>简述<code>grub></code>和<code>grub-rescue></code>的区别.</b></summary><br>

- `grub>` - grub是一个多操作系统引导程序,可以让计算机同时拥有多个操作系统,并在计算机启动时选择希望运行的操作系统.当运行系统的所需文件(除了配置文件)都存在时就进入该模式,该模式下可以访问大多数模块和命令.通过在菜单中按"c"键来调用此模式.
- `grub-rescue` - 如果启动时无法找到grub的目录(特别是包含模块和附加命令的目录,如`/boot/grub/i386-pc`),会进入该模式.如果其中内容已损坏或未找到正常模块,该模式下仅包含基本命令.

</details>

<details>
<summary><b>如何检查私钥和证书是否匹配?</b></summary><br>

```bash
(openssl rsa -noout -modulus -in private.key | openssl md5 ; openssl x509 -noout -modulus -in certificate.crt | openssl md5) | uniq
```

</details>

<details>
<summary><b>如何在不使用<code>useradd</code>/<code>adduser</code>的情况下在系统中添加用户?</b></summary><br>

1. 使用`vipw`在`/etc/passwd`文件添加用户信息条目:

```bash
# username:password:UID:GID:Comments:Home_Directory:Login Shell
user:x:501:501:test user:/home/user:/bin/bash
```

  > 注意语法.且不要用其他文本编辑器编辑该文件.`vipw`会锁定文件,防止其他命令在同时更新.

2. 同时使用`vigr`在/etc/group添加一个同名的组(类似`vipw`):

```bash
user:x:501:
```

3. 为用户设定密码:

```bash
passwd user
```

4. 使用`mkdir`为用户创建家目录:

```bash
mkdir -m 0700 /home/user
```

5. 将`/etc/skel`中的文件复制到新的家目录:

```bash
rsync -av --delete /etc/skel/ /home/user
```

6. 使用`chown`和`chmod`修正用户属组和权限:

```bash
chown -R user:user /home/user
chmod -R go-rwx /home/user
```

参考文档:

- [What steps to add a user to a system without using useradd/adduser?](https://unix.stackexchange.com/questions/153225/what-steps-to-add-a-user-to-a-system-without-using-useradd-adduser)

</details>

<details>
<summary><b>为什么需要<code>mktemp</code>命令?介绍一个实例.</b></summary><br>

`mktemp`可以用随机名称来创建缓存文件.从安全角度上来说,这很重要.

假设下列文件:

```bash
echo "random_string" > /tmp/temp-file
```

用在root运行的脚本中.然后有人读了脚本并做以下操作:

```bash
ln -s /etc/passwd /tmp/temp-file
```

`mktemp`命令可以解决上述问题:

```bash
TEMP=$(mktemp /tmp/temp-file.XXXXXXXX)
echo "random_string" > ${TEMP}
```

现在`ln /etc/passwd`攻击就不会生效了.

</details>

<details>
<summary><b>将<code>strace</code>命令附加到生产环境正在运行的进程中是否安全?会有什么后果?</b></summary><br>

`strace`是Linux的系统调用跟踪器.它目前使用的是所知较少的`ptrace()`(进程跟踪)调试接口,该接口以暴力方式运行:在每次系统调用开始时和结束时都会**暂停目标进程**,以便调试器读取状态.

这意味着`strace`会为了每次系统调用暂停两次应用程序,并在应用程序和`strace`之间进行上下文切换,好比在应用程序上放了交通红绿灯.

后果:

- 会导致明显的巨大的性能开销,最坏情况会使目标应用程序的速度降低100倍以上.这不仅使其不适合在生产环境使用,而且会导致实时信息延迟和误导
- 无法同时跟踪多个进程(被跟踪的子进程除外)
- 只能看到系统调用接口

参考文档:

- [strace Wow Much Syscall (original)](http://www.brendangregg.com/blog/2014-05-11/strace-wow-much-syscall.html)

</details>

<details>
<summary><b>最简单,安全,方便地删除名为<code>-fr</code>目录的方法是什么?</b></summary><br>

以下有效但不太方便:

- `rm -rf -- -fr`
- `perl -le 'unlink("-fr");'`

最方便的方法:

```bash
rm -rf ./-fr
```

</details>

<details>
<summary><b>编写一个或一对简单的用来备份和恢复系统的bash脚本. ***</b></summary><br>

待续.

</details>

###### 网络问题 (24)

<details>
<summary><b>为站点创建SPF记录来控制垃圾邮件. ***</b></summary><br>

待续.

</details>

<details>
<summary><b>权威DNS和非权威DNS的查询结果有什么区别? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>在用<code>host</code>命令解析域名时返回了<code>NXDOMAIN</code>.但实际上<code>resolv.conf</code>存储了2个nameserver且第二个nameserver存储了该域名.为什么本地解析器没有检查第二个nameserver?</b></summary><br>

**NXDOMAIN**表示在Internet上不存在该域名.如果DNS解析不了域名,就会返回**NXDOMAIN**.

`resolv.conf`和`resolver`的默认行为是按服务器列出的顺序来解析的.只有当第一个nameserver超时才会使用下一个nameserver来解析.

其算法是先用第一个nameserver来解析,如果超时则尝试下一个,直到所有的nameserver,然后从头重复直到达到最大重试次数.

如果nameserver以**SERVFAIL**或(**nofail**)或查询超时(**fail**)响应,那么仅使用第一个DNS服务器.

举例:

```
nameserver 192.168.250.20   # 不是dns
nameserver 8.8.8.8          # 没有存储 gate.test.int
nameserver 127.0.0.1        # 存储了 gate.test.int
```

所以当你解析gate.test.int时:

```
host -v -t a gate.test.int
Trying "gate.test.int"                        # 使用第一个dns服务器(192.168.250.20)但是响应超时所以尝试下一个nameserver
Host gate.test.int not found: 3(NXDOMAIN)     # nameserver响应成功但返回了NXDOMAIN(没找到该域名信息)
Received 88 bytes from 8.8.8.8#53 in 43 ms
Received 88 bytes from 8.8.8.8#53 in 43 ms
                                              # 所以列表中最后的nameserver就没用到了
```

为了避免这种情况建议使用`nslookup`等命令,它们可以在第一个nameserver收到**SERVFAIL**时继续使用第二个nameserver.

参考文档:

- [Second nameserver in /etc/resolv.conf not picked up by wget](https://serverfault.com/questions/398837/second-nameserver-in-etc-resolv-conf-not-picked-up-by-wget)

</details>

<details>
<summary><b>探索你的网站的当前MTA配置,并查看目前的MTA有哪些特殊功能? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>可以使用哪些技术/工具来根据IP地址查找域名? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>是否可以直接获得IP地址的SSL证书,而不是域名?</b></summary><br>

只要是公网IP地址就可以,但这很少用到.

SSL证书通常颁布给全限定域名(FQDN),如`https://www.domain.com`.但是,某些组织需要把SSL证书颁发给公共IP地址,则需要通过在证书签名请求(CSR)中将公网IP地址指定为Common Name,这样证书就能用来保障与公网IP的直连安全,如,`https//1.1.1.1`.

根据CA规定,除非IP地址同时位于CommonName和SubjectAltName字段中,否则IP地址证书可能存在兼容性问题.这是由于传统的SSL实现与RFC 5280不一致,特别是Windows 10之前的Windows操作系统.

参考文档:

- [Are SSL certificates bound to the servers ip address?](https://stackoverflow.com/questions/1095780/are-ssl-certificates-bound-to-the-servers-ip-address)
- [SSL certificate for a public IP address?](https://serverfault.com/questions/193775/ssl-certificate-for-a-public-ip-address)

</details>

<details>
<summary><b>如何为网站做负载测试和容量规划? ***</b></summary><br>

待续.

参考文档:

- [How do you do load testing and capacity planning for web sites? (original)](https://serverfault.com/questions/350454/how-do-you-do-load-testing-and-capacity-planning-for-web-sites)
- [Can you help me with my capacity planning?](https://serverfault.com/questions/384686/can-you-help-me-with-my-capacity-planning)
- [How do you do load testing and capacity planning for databases?](https://serverfault.com/questions/350458/how-do-you-do-load-testing-and-capacity-planning-for-databases)

</details>

<details>
<summary><b>开发人员报告了一个连接远程服务的问题.使用<code>/dev</code>来解决问题.</b></summary><br>

```bash
# <host> - set remote host
# <port> - set destination port

# 1
timeout 1 bash -c "</dev/tcp/<host>/<port>" >/dev/null 2>&1 ; echo $?

# 2
timeout 1 bash -c 'cat < /dev/null > /dev/tcp/<host>/<port>' ; echo $?

# 2
&> echo > "</dev/tcp/<host>/<port>"
```

参考文档:

- [Advanced Bash-Scripting Guide - /dev](http://www.tldp.org/LDP/abs/html/devref1.html#DEVTCP)
- [/dev/tcp as a weapon](https://securityreliks.wordpress.com/2010/08/20/devtcp-as-a-weapon/)
- [Test from shell script if remote TCP port is open](https://stackoverflow.com/questions/4922943/test-from-shell-script-if-remote-tcp-port-is-open)

</details>

<details>
<summary><b>在网站或app前安装Varnish是否意味着不再需要关心负载平衡或冗余?</b></summary><br>

不一定.Varnish是一个缓存服务器,因此它的目的是缓存内容并充当反向代理,同时加速数据检索并减少Web服务器的负载.

Varnish也可以配置为多个Web服务器的负载均衡器,但如果只使用一个Varnish服务器,这将成为基础架构上的单点故障.

确保负载平衡或冗余的解决方案是至少两个Varnish实例的集群,并处于主动-主动模式或主动-被动模式.

</details>

<details>
<summary><b>Varnish Cache中的命中次数,未命中次数和hit-for-pass次数是什么?</b></summary><br>

**hit**是一个成功从缓存中获得数据的请求.
**miss**是一个在缓存中找不到数据的请求,因此必须从源文件中获取.
**hit-for-pass**是当Varnish Cache意识到它收到的请求中有对象是不可缓存的,就会返回pass.

参考文档:

- [VCL rules for hits](https://book.varnish-software.com/4.0/chapters/VCL_Subroutines.html#vcl-vcl-hit)
- [VCL rules for hit-for-pass](https://book.varnish-software.com/4.0/chapters/VCL_Subroutines.html#hit-for-pass)
- [Example of the use](https://book.varnish-software.com/4.0/chapters/VCL_Basics.html#vcl-backend-response)

</details>

<details>
<summary><b>根据下列参数给出缓存内容的合理TTL值.? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>开发人员说:<i><code>htaccess</code>充满魔力应该使用它</i>.你对使用<code>htaccess</code>文件有什么看法? 对Web应用程序有什么影响?</b></summary><br>

`.htaccess`文件诞生于共享主机常见的时代:

- 系统管理员需要一种方法来允许多个客户端在不同的帐户下访问其服务器,并为其网站配置不同的配置.

`.htaccess`文件允许用户无需访问整个服务器仍能修改Apache的工作方式.这些文件可存在于网站目录树中的任何目录,并为目录及其中的文件和文件夹提供功能.

**会影响服务器性能**

要使`.htaccess`工作,Apache需要检查所请求路径中的每个目录是否存在`.htaccess`文件,如果存在,则会读取其中的每一个并解析它.每次请求都会发生这种情况.请记住,该文件更改后仍是有效的,因为Apache每次都会读取它.

Web服务器会处理每个请求 - 即使是级别最低的`.png`或`.css`文件 - 这会导致Apache:

- 在当前请求的目录中查找`.htaccess`文件
- 然后在每个目录中查找`.htaccess`文件,直到服务器根目录
- 将所有这些`.htaccess`文件合并在一起
- 使用新设置重新配置Web服务器
- 最后,传递文件

每个网页都会生成数十个请求.这是不必要的开销,更重要的是,这是完全没用的.

**安全和许可**

如果不妥善处理,允许每个用户使用`.htaccess`来修改服务器的配置可能会导致安全问题.因为如果在`.htaccess`文件中添加任何指令,都会视为将其添加到Apache配置文件中.

这意味着非管理员可能会编写这些文件,从而`撤消`所有安全配置.如果需要做一些临时配置,`.htaccess`是一个很好的功能,但如果需要做一些长久的配置,需要把配置放在`/etc/apache/sites-available/site.conf`中(或`httpd.conf`或服务器能调用的任何内容).

**总结**

如果可以访问httpd主服务器配置文件,则应完全避免使用`.htaccess`文件.如果配置在`.htaccess`中生效,它也可以在任何虚拟主机`.conf`文件中生效.

如果无法避免使用`.htaccess`文件,则应遵循这些规则:

- 只使用一个`.htaccess`文件或尽可能少
- 将`.htaccess`文件放在站点根目录中
- 确保`.htaccess`文件简短

参考文档:

- [Like Apache: .htaccess](https://www.nginx.com/resources/wiki/start/topics/examples/likeapache-htaccess/)
- [Don't Use .htaccess Unless You Must](https://www.danielmorell.com/guides/htaccess-seo/basics/dont-use-htaccess-unless-you-must)

</details>

<details>
<summary><b>如何在有和没有SNI(服务器名称指示)的情况下测试与远程主机的连接?在哪些情况下这会很有用?</b></summary><br>

使用<b>OpenSSL</b>:

```bash
# 测试远程连接(with SNI support)
echo | openssl s_client -showcerts -servername google.com -connect google.com:443
# 测试远程连接(without SNI support)
echo | openssl s_client -connect google.com:443 -showcerts
```

使用<b>GnuTLS</b>:

```bash
# 测试远程连接(with SNI support)
gnutls-cli -p 443 google.com
# 测试远程连接(without SNI support)
gnutls-cli --disable-sni -p 443 google.com
```

</details>

<details>
<summary><b>cookie如何在HTTP协议中传递?</b></summary><br>

服务器在其响应头中发送以下内容来设置cookie字段:

`Set-Cookie:name=value`

如果设置了cookie,则浏览器在其请求头中会发送以下内容:

`Cookie:name=value`

</details>

<details>
<summary><b>如何防止未命名的Web服务器的处理请求?未命名服务器的默认名称规则可能是安全问题? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>什么是测试NFS性能的正确方法?
</b></summary><br>

最佳基准是"常用程序".20个人同时编译Linux内核和同样一群人同时登陆操作账户对NFS系统的负载是完全不一样的.

不过我们也有一些很好的测试工具.

- <b>boonie</b> - 一个经典的性能评估工具测试.是一个硬盘和文件系统的基准性能测试工具,它通过一系列的简单测试来生成硬盘和文件系统的性能参数.主要对三个方面做基准测试:数据读/写速度,每秒可以完成的磁盘寻道次数和每秒可以完成的文件元数据操作次数.

- <b>DBench</b> - 用来让独立开发人员调试和测试SAMBA.它由原始的SAMBA工具的启发而来.

- <b>IOZone</b> - 性能测试套件.兼容POSIX和64位.此工具来自L.S.E的文件系统测试.主要功能:POSIX异步I/O,Mmap()文件I/O,普通文件I/O单文件测量,多文件流测量,分布式文件服务器(集群)测量等.

</details>

<details>
<summary><b>需要阻止来自同一子网的多个IP地址,对系统来说遍历iptables规则集或黑洞路由哪个更有效?</b></summary><br>

如果系统的路由表中定义了数千条路由,而iptables规则中没有任何内容,那么输入iptables规则实际上可能更有效.

然而,在大多数系统中,路由表都很小,在这种情况下,使用空路由会更有效.尤其是如果已经有了很多的iptables规则时.

假设阻止是基于源地址而不是目标地址,那么在**raw/PREROUTING**中执行**DROP**就可以了,这样能在做出任何路由决策之前就丢弃数据包.

但请记住,iptables规则本质上是一个链表,为了在阻止大量地址时获得最佳性能,应该使用`ipset`.

另一方面,如果按目标地址阻止,那么在使用路由表和iptables可能没有什么区别,**除非**如果源IP是由欺骗性的.在这种情况下,黑洞条目可能会消耗路由缓存资源,所以**raw/PREROUTING**仍然是首选.

在尝试将数据包发送回攻击者之前,传出路由无关紧要.但那时将承担了大部分设置套接字的成本,甚至可能有线程阻塞等待等网络问题.

iptables或其他防火墙允许系统阻止传入流量并在它到达服务器上的守护程序进程之前将其丢弃.在当前用例中,它似乎显然更优越.

```bash
iptables -A INPUT -s 192.168.200.0/24 -j DROP
```

当你在Linux/Unix系统上定义路由时,它会通知系统将网络通信路由到此指定位置以便与该IP地址进行通信.

当你定义空路由时,它会告诉系统丢弃所有发送给指定IP地址的网络通信.这意味着任何基于TCP的网络通信将无法建立,因为服务器将无法再发送SYN/ACK回复.任何基于UDP的网络通信仍能被接收,但是系统将不再向原始IP发送任何响应.

同时,iptables可以在链中创建数万条规则,但链是按顺序遍历,直到在每个数据包上找到对应匹配的.因此,大量规则可能导致系统花费大量的CPU时间.

路由规则比iptables简单得多.iptables可以基于许多不同的变量,包括协议,源和目标数据包,甚至是在当前数据包之前发送的其他数据包来进行匹配.

而在路由规则中,最重要的就是远程IP地址,因此非常容易优化.此外,许多系统都有很多路由规则.典型的系统可能只有5或10个,但充当BGP路由器的系统可能有数万个.所以,在很长一段时间内都在持续优化为特定数据包选择正确的路由.

在技术方面意味着系统将从攻击者那里接收数据,但不对其做出响应.

```bash
ip route add blackhole 192.168.200.0/24
```

或

```bash
ip route add 192.168.200.0/24 via 127.0.0.1
```

参考文档:

- [The difference between iptables DROP and null-routing.](https://www.tummy.com/blogs/2006/07/27/the-difference-between-iptables-drop-and-null-routing/)

</details>

<details>
<summary><b>如何使用<code>scp</code>操作第2个远程主机?</b></summary><br>

使用`ssh`:

```bash
ssh user1@remote1 'ssh user2@remote2 "cat file"' > file
```

使用`tar` (使用压缩):

```bash
ssh user1@remote1 'ssh user2@remote2 "cd path2; tar cj file"' | tar xj
```

使用`ssh`和端口转发隧道:

```bash
#首先,打开隧道
ssh -L 1234:remote2:22 -p 45678 user1@remote1

#然后使用隧道直接从remote2复制文件
scp -P 1234 user2@localhost:file .
```

</details>

<details>
<summary><b>如何减少动态网站的加载时间?</b></summary><br>

- 优化网页
- 缓存网页
- 优质的网络托管
- 压缩文本文件
- apache/nginx调优

</details>

<details>
<summary><b>在浏览器中键入api.example.com并按回车键时,哪些类型的dns缓存会生效?</b></summary><br>

浏览器先检查该域名是否在其缓存中(要查看Chrome中的DNS缓存,请转到`chrome//net-internals/#dns`).当该缓存查询失败时,它会要求操作系统来解析.

操作系统会检查其解析器自己的缓存.如果查询失败,它会转向询问操作系统配置的DNS服务器.

操作系统配置的DNS服务器通常由DHCP从路由器配置,一般是ISP的DNS服务器,由DHCP从Internet网关传到路由器.

如果路由器拥有自己的DNS服务器,它可能拥有自己的缓存,否则只要发现操作系统缓存为空,就应该直接指向ISP的DNS服务器.

参考文档:

- [What happens when...](https://github.com/alex/what-happens-when)
- [DNS Explained - How Your Browser Finds Websites](https://scotch.io/tutorials/dns-explained-how-your-browser-finds-websites)
- [Firefox invalidate dns cache](https://stackoverflow.com/questions/13063496/firefox-invalidate-dns-cache)

</details>

<details>
<summary><b><code>Cache-Control: max-age=0</code>和<code>Cache-Control: no-cache</code>的不同之处是什么?</b></summary><br>

**从源服务器发送**

`max-age=0`只是用来告诉缓存(和客户端)响应从一开始就是陈旧的,所以它们**应该**在使用缓存副本之前重新验证响应(例如使用If-Not-Modified标头)而`no-cache`告诉他们**必须**在使用缓存副本之前重新验证.

换句话说,缓存有时可能会选择使用陈旧的响应(虽然我认为他们必须添加一个警告标题),但是`no-cache`表示无论如何都不允许使用陈旧的响应.

**从客户端发送**

如果客户端发送带有`Cache-Control:max-age=0`(又称"端到端重新验证")的请求,则沿途的每个缓存将重新验证其缓存条目(如使用If-Not-Modified header)直到源服务器.如果回复是304(未修改),则可以使用该缓存.

另一方面,发送带有`Cache-Control:no-cache`(又称"端到端重新加载")的请求不会让缓存重新生效,服务器在响应时不得使用缓存副本.

</details>

<details>
<summary><b>设置<code>Access-Control-Allow-Origin</code>有哪些安全隐患?</b></summary><br>

请求的资源通过<code>Access-Control-Allow-Origin: *</code>响应表示该资源允许与每个源共享.这基本上意味着任何站点都可以向你的站点发送XHR请求并访问服务器的响应,如果你没有实现此CORS响应,则不会出现这种情况.

因此,任何网站都可以代表其访问者向你的网站提出请求并处理其响应.如果网站使用了的某些类似基于浏览器自动提供的内容的身份验证或授权方案(Cookie,基于cookie的会话等)等功能,那么第三方站点触发的请求也将使用它们.

</details>

<details>
<summary><b>使用<code>netcat</code>来创建一次性TCP或UDP代理.</b></summary><br>

```bash
### TCP -> TCP
nc -l -p 2000 -c "nc [ip|hostname] 3000"

### TCP -> UDP
nc -l -p 2000 -c "nc -u [ip|hostname] 3000"

### UDP -> UDP
nc -l -u -p 2000 -c "nc -u [ip|hostname] 3000"

### UDP -> TCP
nc -l -u -p 2000 -c "nc [ip|hostname] 3000"
```

</details>

<details>
<summary><b>使用<code>nmap</code>来简析3种回避防火墙的技术.</b></summary><br>

**使用诱饵地址**

```bash
# 生成随机数量的诱饵.
nmap -D RND:10 [target]

# 手动指定诱饵的IP地址.
nmap -D decoy1,decoy2,decoy3 [target]
```

在这种类型的扫描中,可以指示Nmap欺骗来自其他主机的数据包.在防火墙日志中,它不仅包括真实的IP地址,还有诱饵的IP地址,因此要判断是哪个IP进行的扫描将更加困难.

**规范源端口号**

```bash
nmap --source-port 53 [target]
```

许多管理员在配置防火墙时遇到的常见错误是:设置允许来自特定端口号的所有传入流量的规则.Nmap的<code>--source-port</code>选项可利用这种错误配置.用于此类扫描的常用端口是:20,53和67.

**附加随机数据**

```bash
nmap --data-length 25 [target]
```

许多防火墙通过查看其大小来检查数据包,以便识别潜在的端口扫描.这是因为许多扫描程序会发送具有特定大小的数据包.为了避免这种检测,可以使用命令<code>--data-length</code>来添加其他数据并发送大小不同于默认值的数据包.

**扫描TCP ACK**

```bash
nmap -sA [target]
```

发送ACK数据包而不是SYN数据包总是好的,由于防火墙将ACK数据包视为SYN的响应包,所以任何远程计算机上的防火墙即使收到ACK数据包也无法创建日志.

参考文档:

- [Nmap - Techniques for Avoiding Firewalls](https://pentestlab.blog/2012/04/02/nmap-techniques-for-avoiding-firewalls/)

</details>

###### Devops问题 (5)

<details>
<summary><b>简述Flap Detection在Nagios中是如何工作的?</b></summary><br>

当服务或主机的状态频繁更改时就会发生**Flapping**,这会产生很多报警和报警恢复通知.

一旦定义了**Flapping**,即告诉Nagios如何检测**Flapping**,那么每当Nagios检查主机或服务的状态时,将先检查它是否已经开始或停止振荡.

Nagios遵循以下给定的程序来做到这一点：

- 存储分析最后21次主机或服务历史检查的检查结果,并确定状态变化/转换发生的位置
- 使用状态转换来确定主机或服务的状态变化值百分比
- 将状态变化值百分比与抖动阈值的高低进行比较

</details>

<details>
<summary><b>容器化相对于虚拟化有什么优势?</b></summary><br>

以下是容器化相对于虚拟化的优势:

- 容器提供实时配置和可扩展性,VMs提供延迟的配置
- 与VMs相比,容器是轻量级的
- 与容器相比,VMs的性能有限
- 与VMs相比,容器具有更好的资源利用率

</details>

<details>
<summary><b>从Docker Hub安装Docker应用程序(例如Apache,MySQL)的方式是否适用于生产环境?简述其中的安全问题和解决方案.***</b></summary><br>

待续.

</details>

<details>
<summary><b>简介根据下列要求的LXC和LXD的一些常见用例.</b></summary><br>

- 需要隔离的开发环境,同时不污染主机
- 隔离生产服务器,以及在容器中运行多个服务的可能性
- 需要测试在不同操作系统环境下同一软件的多个版本
- 无需在物理主机上安装即可尝试不同的或新版本的GNU/Linux发行版
- 尝试一些软件或开发堆栈,可能会或可能不会在以后使用
- 在主开发机器或生产服务器中安装多种类型的软件,并在较长时间内维护它们
- 在生产机器上实际执行任何安装或维护任务之前先演示运行
- 通过为不同用户或客户端运行多个服务,更好地利用和分配服务器资源
- 高密度的虚拟专用服务器(VPS),可以实现托管隔离而无需完全虚拟化的成本
- 与虚拟机的复杂访问方法相比,从容器可以轻松访问主机硬件
- 具有不同自定义的多个构建环境

</details>

<details>
<summary><b>如何确保Redis集群的安全?</b></summary><br>

- 通过防火墙保护特定的Redis实例免受外部访问
- 如果只有本地客户端访问它,则将其绑定到127.0.0.1
- 沙盒环境
- 启用**AUTH**
- 启用**保护模式**
- 使用数据加密(如`spiped`)
- 禁用特定命令
- 使用**ACLs**

参考文档:

- [Redis Security](https://redis.io/topics/security)
- [A few things about Redis security](http://antirez.com/news/96)

</details>

###### 网络安全问题 (5)

<details>
<summary><b>什么是OWASP应用安全验证标准?请简述. ***</b></summary><br>

待续.

</details>

<details>
<summary><b>什么是CSRF?</b></summary><br>

**跨站请求伪造**是一个Web应用程序漏洞.服务端会直接处理该请求而不会检查该请求是否来自可信客户端.CSRF攻击者在用户已经登录目标网站之后,诱使用户访问一个攻击页面,利用目标网站对用户的信任,以用户身份在攻击页面对目标网站发起伪造用户操作的请求,从而达到攻击目的.

</details>

<details>
<summary><b>策略,流程和指南之间有什么区别?</b></summary><br>

**安全策略**定义了组织的安全目标和安全框架.**流程**是一个详细的步骤,用来记录一步步实施重要安全机制所需的确切操作.**指南**是可以变动的提议,用于创建流程.

</details>

<details>
<summary><b>在IDS(入侵检测系统)中,什么是false positive和false negative?</b></summary><br>

如果系统设备生成实际未发生入侵的警报时:这是**false positive**.如果系统设备没有生成任何警报但实际发生了入侵:这是**false negative**.

</details>

<details>
<summary><b>Web服务器强化的10个点.</b></summary><br>

例如:

- 如果是新安装的服务器,请保护其免受恶意网络流量的影响,直到安装并加固操作系统
- 为`/tmp`创建一个单独的分区,并将选项设置为`nodev`,`nosuid`和`noexec`
- 为`/var`,`/var/log`,`/var/log/audit`和`/home`创建单独的分区
- 启用虚拟内存随机域
- 删除遗留服务,如`telnet-server`,`rsh`,`rlogin`,`rcp`,`ypserv`,`ypbind`,`tftp`,`tftp-server`,`talk`,`talk-server`
- 通过防火墙和其他访问控制技术,限制认证用户的服务与主机上运行的服务连接
- 禁止接收源路由数据包
- 启用**TCP/SYN**cookie
- 禁用SSH root登录
- 安装和配置**AIDE**
- 安装和配置**OSsec HIDS**
- 配置**SELinux**
- 所有管理员或root访问记录都必须被记录
- 启用并测试系统帐户,组成员身份及其相关权限的完整性检查
- 设置密码创建要求(如使用PAM)

参考文档:

- [Security Harden CentOS 7](https://highon.coffee/blog/security-harden-centos-7/)
- [CentOS 7 Server Hardening Guide](https://www.lisenet.com/2017/centos-7-server-hardening-guide/)

</details>

## 隐秘的知识

### :diamond_shape_with_a_dot_inside: 资深系统管理员

<details>
<summary><b>应用程序遇到一些性能问题,需要找到要优化的代码.如何在Linux环境中配置来实现?</b></summary><br>

>理想情况下,需要一个应用程序可以附加到进程并定期记录快照:线程的内存使用数和CPU使用率等.

1. 在批处理模式下使用`top`.它以批处理模式运行,直到它被终止或直到N次迭代完成:

```bash
top -b -p `pidof a.out`
```

或

```bash
top -b -p `pidof a.out` -n 100
```

2. 也可以使用ps(例如在shell脚本中):

```bash
ps --format pid,pcpu,cputime,etime,size,vsz,cmd -p `pidof a.out`
```

>需要一些方法来记录Linux机器上的应用程序的性能.

1. 记录性能数据:

```bash
perf record -p `pidof a.out`
```

记录10s:

```bash
perf record -p `pidof a.out` sleep 10
```

调用图形界面记录:

```bash
perf record -g -p `pidof a.out`
```

2) 分析记录的数据

```bash
perf report --stdio
perf report --stdio --sort=dso -g none
perf report --stdio -g none
perf report --stdio -g
```

**这是一个分析测试程序的示例**

1. 运行程序(c++):

```bash
./my_test 100000000
```

2. 记录运行中程序的性能数据:

```bash
perf record -g  -p `pidof my_test` -o ./my_test.perf.data sleep 30
```

3. 分析每个模块的负载:

```bash
perf report --stdio -g none --sort comm,dso -i ./my_test.perf.data

# Overhead  Command                 Shared Object
# ........  .......  ............................
#
    70.06%  my_test  my_test
    28.33%  my_test  libtcmalloc_minimal.so.0.1.0
     1.61%  my_test  [kernel.kallsyms]
```

4. 分析每个函数的负载:

```bash
perf report --stdio -g none -i ./my_test.perf.data | c++filt

# Overhead  Command                 Shared Object                       Symbol
# ........  .......  ............................  ...........................
#
    29.30%  my_test  my_test                       [.] f2(long)
    29.14%  my_test  my_test                       [.] f1(long)
    15.17%  my_test  libtcmalloc_minimal.so.0.1.0  [.] operator new(unsigned long)
    13.16%  my_test  libtcmalloc_minimal.so.0.1.0  [.] operator delete(void*)
     9.44%  my_test  my_test                       [.] process_request(long)
     1.01%  my_test  my_test                       [.] operator delete(void*)@plt
     0.97%  my_test  my_test                       [.] operator new(unsigned long)@plt
     0.20%  my_test  my_test                       [.] main
     0.19%  my_test  [kernel.kallsyms]             [k] apic_timer_interrupt
     0.16%  my_test  [kernel.kallsyms]             [k] _spin_lock
     0.13%  my_test  [kernel.kallsyms]             [k] native_write_msr_safe

  ...
```

5. 分析调用链:

```bash
perf report --stdio -g graph -i ./my_test.perf.data | c++filt

# Overhead  Command                 Shared Object                       Symbol
# ........  .......  ............................  ...........................
#
    29.30%  my_test  my_test                       [.] f2(long)
            |
            --- f2(long)
               |
                --29.01%-- process_request(long)
                          main
                          __libc_start_main

    29.14%  my_test  my_test                       [.] f1(long)
            |
            --- f1(long)
               |
               |--15.05%-- process_request(long)
               |          main
               |          __libc_start_main
               |
                --13.79%-- f2(long)
                          process_request(long)
                          main
                          __libc_start_main

  ...
```

所以这样能知道程序在哪里花费的时间比较长.

另外,还可以使用`pstack`或`lsstack`.

其他工具有Valgrind.首先运行:

```bash
valgrind --tool=callgrind --dump-instr=yes -v --instr-atstart=no ./binary > tmp
```

当它工作且我们需要分析时,应该在另一个窗口运行:

```bash
callgrind_control -i on
```

分析一段时间后,需要关闭并停止整个任务,则输入:

```bash
callgrind_control -k
```

当前目录中会有一些callgrind.out.*的文件.查看分析结果则使用:

```bash
kcachegrind callgrind.out.*
```

建议在下一个窗口中单击**Self**列标题,否则显示`main()`是最耗时的任务.

参考文档:

- [Tracing processes for fun and profit](http://techblog.rosedu.org/tracing-processes-for-fun-and-profit.html)

</details>

<details>
<summary><b>Linux系统上只安装了有限数量的软件包,且telnet不可用.如何使用sysfs虚拟文件系统测试所有接口上的连接(除了环回地址).</b></summary><br>

举例:

```bash
#!/usr/bin/bash

for iface in $(ls /sys/class/net/ | grep -v lo) ; do

  if [[ $(cat /sys/class/net/$iface/carrier) = 1 ]] ; then state=1 ; fi

done

if [[ $state -ne 0 ]] ; then echo "not connection" > /dev/stderr ; exit ; fi
```

</details>

<details>
<summary><b>需要使用负载将POST重写为外部API,但POST请求会丢失URL上传递的参数.如何解决这个问题(如在Nginx中)以及这种行为的原因是什么?</b></summary><br>

这个问题是由于外部重定向永远不会重发**POST**数据.这是写入HTTP规范的(查看`3xx`部分).任何执行此操作的客户端都违反了规范.

**POST**数据应该在请求正文中传递,如果执行了标准重定向,则会丢弃该数据.

如下:

```
   +-------------------------------------------+-----------+-----------+
   |                                           | Permanent | Temporary |
   +-------------------------------------------+-----------+-----------+
   |  允许将请求方法从POST更改为GET              | 301       | 302       |
   |  不允许将请求方法从POST更改为GET            | 308       | 307       |
   +-------------------------------------------+-----------+-----------+
```

可以尝试使用HTTP状态代码**307**,任何符合RFC的浏览器就会重复发布请求.只需要编写一个HTTP状态代码为**307**或**308**的Nginx重写规则即可:

```bash
location / {
    proxy_pass              http://localhost:80;
    client_max_body_size    10m;
}

location /api {
    # HTTP 307 only for POST method.
    if ($request_method = POST) {
        return 307 https://api.example.com?request_uri;
    }

    # You can keep this for non-POST requests.
    rewrite ^ https://api.example.com?request_uri permanent;

    client_max_body_size    10m;
}
```

应使用HTTP状态代码**307**或**308**来代替**301**,因为**301**会把请求方法从**POST**更改为**GET**.

参考文档:

- [Redirection on Apache (Maintain POST params)](https://stackoverflow.com/questions/17295085/redirection-on-apache-maintain-post-params)
- [Why doesn't HTTP have POST redirect?](https://softwareengineering.stackexchange.com/questions/99894/why-doesnt-http-have-post-redirect)

</details>

<details>
<summary><b>写两条黄金法则来减少黑客入侵系统的影响.</b></summary><br>

1) **最小特权原则**

应该将服务配置为由完成服务任务所需的最小权限的用户来运行,这样即使黑客侵入也能有效限制他们.

例如,使用zero-day攻击进入Apache webserver服务器的黑客只能使用该进程可以访问的系统内存和文件资源.黑客能够下载html和php源文件,并可能会查看mysql数据库,但他们不能获得root权限或超出apache可访问的文件.

许多Apache webserver在安装时会默认创建'apache'用户和组,这样可以在Apache主配置文件(`httpd.conf`)配置以便让这些组运行apache.

2) **特权分离原则**

如果网站只需要对数据库有只读访问权限,则创建只有只读权限的帐户,且仅创建该数据库.

**SElinux**是创建安全环境的不错选择,`app-armor`是另一种工具.**Bastille**则是强化前的首选.

通过将已被泄露的服务的功能分离到其自己的"Box"中来减少任何攻击的影响.

3) **使用白名单而不是黑名单**

白名单比黑名单更安全.

一个专属俱乐部永远不会试图列出所有不能进来的人;他们会列出所有可以进入的人,并排除那些不在列表中的人.

同样,尝试列出所有不应该访问机器的内容也是注定要失败的.列表限制程序/IP地址/用户的访问将更有效.

当然,和其他任何事情一样,这涉及一些权衡.具体而言,白名单非常不方便并且需要不断维护.

为了在权衡中更进一步,可以通过断开计算机与网络的连接来获得极大的安全性.

**其他要点**:

使用可用的工具.我们很难做到像安全专家一样好,所以要用其他工具来保护自己.

- 公钥加密提供了出色的安全性
- 强制执行密码复杂性
- 了解为什么要对上述规则进行例外处理 - 定期审查例外情况
- 让某人为失败负责会让你保持警觉

参考文档:

- [How to prevent zero day attacks (original)](https://serverfault.com/questions/391370/how-to-prevent-zero-day-attacks)

</details>

<details>
<summary><b>如何使用<code>curl</code>测量一次请求和响应的时间?</b></summary><br>

`curl`支持格式化输出以获取请求的详细信息(关于详细信息请参阅`curl`的帮助文档,在`-w| -write-out 'format'`中).基于题目目的,我们将仅关注所提供的时序细节.

1. 创建新文件`curl-format.txt`,并复制下文:

```bash
    time_namelookup:  %{time_namelookup}\n
       time_connect:  %{time_connect}\n
    time_appconnect:  %{time_appconnect}\n
   time_pretransfer:  %{time_pretransfer}\n
      time_redirect:  %{time_redirect}\n
 time_starttransfer:  %{time_starttransfer}\n
                    ----------\n
         time_total:  %{time_total}\n
```

2. 请求:

```bash
curl -w "@curl-format.txt" -o /dev/null -s "http://example.com/"
```

该命令做了什么:

- `-w "@curl-format.txt"` - 让cURL使用格式化文件
- `-o /dev/null` - 重定向请求的输出到/dev/null
- `-s` - 让cURL不显示进度表
- `http://example.com/` - 请求的地址.如果URL具有"&"查询字符串参数,请使用引号.

</details>

<details>
<summary><b>什么原因需要把ext4 journal移动到另一个磁盘/分区上? ***</b></summary><br>

待续.

参考文档:

- [ext4: using external journal to optimize performance](https://raid6.com.au/posts/fs_ext4_external_journal/)
- [How to move an ext4 journal](https://unix.stackexchange.com/questions/278998/how-to-move-an-ext4-journal)

</details>

<details>
<summary><b>假设你正在参加安全会议.成员们争论如何在网络核心上安装OpenBSD防火墙.请去讲台并表达对此解决方案的看法,比如有什么利弊和原因? ***</b></summary><br>

待续.

</details>

<details>
<summary><b>有没有办法在Nginx中使用Access-Control-Allow-Origin标头来允许多个跨域?</b></summary><br>

此正则表达式可以轻松匹配域和子域列表:

```bash
location ~* \.(?:ttf|ttc|otf|eot|woff|woff2)$ {
   if ( $http_origin ~* (https?://(.+\.)?(domain1|domain2|domain3)\.(?:me|co|com)$) ) {
      add_header "Access-Control-Allow-Origin" "$http_origin";
   }
}
```

更详细的配置:

```bash
location / {

    if ($http_origin ~* (^https?://([^/]+\.)*(domainone|domaintwo)\.com$)) {
        set $cors "true";
    }

    # Nginx doesn't support nested If statements. This is where things get slightly nasty.
    # Determine the HTTP request method used
    if ($request_method = 'GET') {
        set $cors "${cors}get";
    }
    if ($request_method = 'POST') {
        set $cors "${cors}post";
    }

    if ($cors = "true") {
        # Catch all in case there's a request method we're not dealing with properly
        add_header 'Access-Control-Allow-Origin' "$http_origin";
    }

    if ($cors = "trueget") {
        add_header 'Access-Control-Allow-Origin' "$http_origin";
        add_header 'Access-Control-Allow-Credentials' 'true';
        add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS';
        add_header 'Access-Control-Allow-Headers' 'DNT,X-CustomHeader,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type';
    }

    if ($cors = "truepost") {
        add_header 'Access-Control-Allow-Origin' "$http_origin";
        add_header 'Access-Control-Allow-Credentials' 'true';
        add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS';
        add_header 'Access-Control-Allow-Headers' 'DNT,X-CustomHeader,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type';
    }

}
```

</details>

<details>
<summary><b><code>:(){ :|:& };:</code>是什么,以及当你登陆系统后如何停止该代码?</b></summary><br>

这是一个**fork炸弹**.

- `:()` - 定义了一个函数.`:`是函数名称,空括号表示它不接受任何参数
- `{ }` - 这些字符显示了定义函数的开头和结尾
- `:|:` - 这个将`:`函数副本加载到内存中并通过管道输出给另一个`:`函数副本,这些都需要加载到内存中.
- `&` - 这将使进程成为后台进程,这样即使父进程被自动终止,子进程也不会被杀死
- `:` - 最后的`:`会执行这个函数并导致连锁反应.

保护多用户系统的最佳方法是使用**PAM**来限制用户可以使用的进程数.fork炸弹最大的问题是它占用了过多的过程资源.

因此,如果已登录系统,我们有两种方法来尝试解决此问题:
- 执行**SIGSTOP**命令来停止进程:`killall -STOP -u user1`
- 如果不能在命令行运行,那么就不得不使用`exec`强制它运行(由于所有进程都被使用):`exec killall -STOP -u user1`

防止fork炸弹最好的方法就是避免出现问题.

</details>

<details>
<summary><b>如何恢复已经删除但Apache仍保持打开的文件?</b></summary><br>

如果文件已被删除但仍处于打开状态,则表示该文件仍存在于文件系统中(它具有inode)但其硬链接数为0.由于没有指向该文件的链接,因此无法按名称打开该文件,同时也无法仅靠inode打开文件.

Linux通过`/proc`下的特殊符号链接显示打开的文件.这些链接称为`/proc/12345/fd/42`,其中12345是进程的**PID**,42是该进程中的文件描述符的编号.与该进程同一用户运行的程序可以访问该文件(读取/写入/执行权限与删除文件时的权限相同).

在符号链接的目标中仍然可以看到打开文件的名称:如果文件是`/var/log/apache/foo.log`,那么链接的目标是`/var/log/apache/foo.log(deleted)`.

因此可以恢复打开的已删除文件的内容,前提是知道已打开的进程的**PID**以及打开它的描述符,如下所示:

```bash
recover_open_deleted_file () {
  old_name=$(readlink "$1")
  case "$old_name" in
    *' (deleted)')
      old_name=${old_name%' (deleted)'}
      if [ -e "$old_name" ]; then
        new_name=$(TMPDIR=${old_name%/*} mktemp)
        echo "$oldname has been replaced, recovering content to $new_name"
      else
        new_name="$old_name"
      fi
      cat <"$1" >"$new_name";;
    *) echo "File is not deleted, doing nothing";;
  esac
}
recover_open_deleted_file "/proc/$pid/fd/$fd"
```

如果只知道进程的**ID**但不知道文件描述符,则可以恢复所有文件:

```bash
for x in /proc/$pid/fd/* ; do
  recover_open_deleted_file "$x"
done
```

如果连进程的**ID**也不知道,则可以搜索所有进程:

```bash
for x in /proc/[1-9]*/fd/* ; do
  case $(readlink "$x") in
    /var/log/apache/*) recover_open_deleted_file "$x";;
  esac
done
```

还可以通过解析`lsof`的输出来获取此列表,但它并不简单也不可靠更不可移植(无论如何这都是Linux特定的).

</details>

<details>
<summary><b>你必须远程在其中一台主要的服务器上重新安装系统,但是无法访问管理控制台(例如iDRAC).如何在已有Linux系统存在并运行的磁盘上安装Linux?</b></summary><br>

可能的问题应该是:"_从系统级别安装系统并代替其他系统工作_".

以Debian GNU/Linux发行版为例:

1. 创建工作目录并使用debootstrap工具下载系统.

```bash
_working_directory="/mnt/system"
mkdir $_working_directory
debootstrap --verbose --arch amd64 {wheezy|jessie} . http://ftp.en.debian.org/debian
```

2. 挂载子系统:`proc`, `sys`, `dev`和`dev/pts`.

```bash
for i in proc sys dev dev/pts ; do mount -o bind $i $_working_directory/$i ; done
```

3. 备份系统以便还原.

```bash
cp system_backup_22012015.tgz $_working_directory/mnt
```

但是,最好不要浪费空间并以不同的方式进行(假设备份位于`/mnt/backup`中):

```bash
_backup_directory="${_working_directory}/mnt/backup"
mkdir $_backup_directory && mount --bind /mnt/backup $_backup_directory
```

4. Chroot到"新"系统.

```bash
chroot $_working_directory /bin/bash
```

5. 更新挂载设备的信息.

```bash
grep -v rootfs /proc/mounts > /etc/mtab
```

6. 在"新"的系统中,接下来要做的就是挂载"旧"系统所在位置的磁盘(如`/dev/sda1`).

```bash
_working_directory="/mnt/old_system"
_backup_directory="/mnt/backup"
mkdir $_working_directory && mount /dev/sda1 $_working_directory
```

7. 删除所有旧系统的文件.

```bash
for i in $(ls | awk '!(/proc/ || /dev/ || /sys/ || /mnt/)') ; do rm -fr $i ; done
```

8. 下一步从备份中恢复系统.

```bash
tar xzvfp $_backup_directory/system_backup_22012015.tgz -C $_working_directory
```

9. 将下列目录`proc`,`sys`,`dev`和`dev/pts`挂载到新的工作目录.

```bash
for i in proc sys dev dev/pts ; do mount -o bind $i $_working_directory/$i ; done
```

10. 安装和更新grup配置.

```bash
chroot $_working_directory /bin/bash -c "grub-install --no-floppy --root-directory=/ /dev/sda"
chroot $_working_directory /bin/bash -c "update-grub"
```

11. 卸载`proc`, `sys`, `dev`和`dev/pts`的文件系统.

```bash
cd
grep $_working_directory /proc/mounts | cut -f2 -d " " | sort -r | xargs umount -n
```

所有命令,如`halt`,`shutdown`或`reboot`,需要重新加载系统配置,不然都不可用. - 为此,请使用**内核调试器**(除了'**b**'选项):

```bash
echo 1 > /proc/sys/kernel/sysrq
echo reisu > /proc/sysrq-trigger
```

当然,建议完全重启机器以完全加载当前系统.如下操作:

```bash
sync ; reboot -f
```

</details>

<details>
<summary><b>在Rsync一个50G的单文件时触发了Linux OOM killer.OOM killer如何决定先杀死哪个进程?如何控制这一切?</b></summary><br>

主流发行版的内核将`/proc/sys/vm/overcommit_memory`的默认值设置为零,这意味着进程可以请求比系统中当前可用的内存更多的内存.

如果内存被进程彻底耗尽,并到了可能威胁系统稳定性的程度上,那么**OOM killer**就会出现.

注意:**OOM Killer**的任务是持续杀死进程,直到释放足够的内存以使内核尝试运行的其余进程顺利运行.

**OOM Killer**会选择最佳进程来杀死.最佳进程是指在杀死时释放最大内存的过程,且对系统来说也是最不重要的.

主要目标是杀死最少数量的进程,最大限度地减少所造成的损害,同时释放最大化的内存量.

为了实现这一点,内核为每个进程都维护了一个`oom_score`参数,可以在`/proc`文件系统中对应pid目录下看到每个进程的oom_score.

>在分析OOM杀手日志时,重要的是查看触发它的内容.

```bash
cat /proc/10292/oom_score
```

进程的`oom_score`值越高,在内存不足的情况下被**OOM Killer**杀死的可能性就越高.

如果想创建一个特殊的控制组,用来提示**OOM Killer**优先杀死的进程列表,那么请在`/mnt/oom-killer`下创建一个目录来表示:

```bash
mkdir lambs
```

将`oom.priority`设置为一个足够高的值:

```bash
echo 256 > /mnt/oom-killer/lambs/oom.priority
```

`oom.priority`是一个64位的无符号整数,且可以取值为最大的64位的无符号整数.在扫描需要杀死的进程时,**OOM-killer**会从进程列表中选择`oom.priority`值最大的进程.

将进程PID添加到进程列表中:

```bash
echo <pid> > /mnt/oom-killer/lambs/tasks
```

要创建一个不会被**OOM-killer**杀死的进程列表,请创建一个包含进程的目录:

```bash
mkdir invincibles
```

将`oom.priority`设置为零会使此cgroup中的所有进程从要杀死的目标进程列表中排除.

```bash
echo 0 > /mnt/oom-killer/invincibles/oom.priority
```

要向该组添加更多进程,请将进程的pid添加到该组中的进程列表中:

```bash
echo <pid> > /mnt/oom-killer/invincibles/tasks
```

参考文档:

- [Rsync triggered Linux OOM killer on a single 50 GB file](https://serverfault.com/questions/724469/rsync-triggered-linux-oom-killer-on-a-single-50-gb-file)

</details>

<details>
<summary><b>什么是salted hashes?使用salt为<code>/etc/shadow</code>文件生成密码.</b></summary><br>

**Salt**基本上就是随机数据.当受适当保护的密码系统收到新密码时,它将为该密码创建哈希值和新的随机salt值,然后将该组合值存储在其数据库中.这有助于抵御字典攻击和已知的哈希攻击.

例如,如果用户在两个不同的系统上使用相同的密码和相同的哈希算法,则最终可能会得到相同的哈希值.但是,只要其中一个系统使用了salt,那么最后的哈希值就不会相同.

`/etc/shadow`文件中的加密密码以下列格式存储:

```bash
$ID$SALT$ENCRYPTED
```

`$ID`表示加密类型,`$SALT`是随机(最多16个字符)字符串,`$ENCRYPTED`是哈希后的密码.

<table style="width:100%">
  <tr>
    <th>Hash类型</th>
    <th>ID</th>
    <th>Hash长度</th>
  </tr>
  <tr>
    <td>MD5</td>
    <td>$1</td>
    <td>22字符</td>
  </tr>
  <tr>
    <td>SHA-256</td>
    <td>$5</td>
    <td>43字符</td>
  </tr>
  <tr>
    <td>SHA-512</td>
    <td>$6</td>
    <td>86字符</td>
  </tr>
</table>

使用Linux shell中的以下命令为`/etc/shadow`生成带随机salt的哈希密码:

- 生成**MD5**哈希密码

```bash
python -c "import random,string,crypt; randomsalt = ''.join(random.sample(string.ascii_letters,8)); print crypt.crypt('MySecretPassword', '\$1\$%s\$' % randomsalt)"
```

- 生成**SHA-256**哈希密码

```bash
python -c "import random,string,crypt; randomsalt = ''.join(random.sample(string.ascii_letters,8)); print crypt.crypt('MySecretPassword', '\$5\$%s\$' % randomsalt)"
```

- 生成**SHA-512**哈希密码

```bash
python -c "import random,string,crypt; randomsalt = ''.join(random.sample(string.ascii_letters,8)); print crypt.crypt('MySecretPassword', '\$6\$%s\$' % randomsalt)"
```

</details>

<details>
<summary><b>有很多套接字挂在<code>TIME_WAIT</code>.且代理服务器后的http服务也有很多小http请求.如何检查并减少<code>TIME_WAIT</code>套接字? ***</b></summary><br>

待续.

参考文档:

- [How to reduce number of sockets in TIME_WAIT?](https://serverfault.com/questions/212093/how-to-reduce-number-of-sockets-in-time-wait)

</details>