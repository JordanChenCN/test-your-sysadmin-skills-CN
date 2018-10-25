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
- 如果你正在采访我,你有什么想问的,前提是我非常擅长处理突发状况?

## 基本知识

### :diamond_shape_with_a_dot_inside: 初级系统管理员

###### 系统方面的问题 (31)

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

更多信息建议阅读有关GNU,Linux,BSD和UNIX起源的文章.虽然这些文章更倾向于个人的理解,但可以让你更好的了解GNU,Linux,BSD和UNIX的差异.

参考文档:
- [What is the difference between Unix, Linux, BSD and GNU? (original)](https://unix.stackexchange.com/questions/104714/what-is-the-difference-between-unix-linux-bsd-and-gnu)
- [The Great Debate: Is it Linux or GNU/Linux?](https://www.howtogeek.com/139287/the-great-debate-is-it-linux-or-gnulinux/)

</details>

<details>
<summary><b>什么是CLI,并说说你最喜欢的CLI命令,小技巧等?</b></summary><br>

**CLI** 是Command Line Interface的缩写.命令行是管理系统最有用的方式之一.
在Linux中,**CLI** 就是这个让用户输入命令完成任务的接口,CLI非常强大,但要避免输错.

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

BASH是我的最爱.它很棒,非常方便,我喜欢它的语法,它的输出输入重定向语法(`>>`, `<< 2>&1`, `2>`, `1>`, etc)和C++差不多,对我更合适.

我也喜欢ZSH,它比BASH更容易定制.它有很棒的Oh-My-Zsh框架,基于tab的强大的上下文联系,模式匹配/globbing on steroids(不懂),可加载模块以及更多.

参考文档:
- [Comparison of command shells](https://en.wikipedia.org/wiki/Comparison_of_command_shells)

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
<summary><b>谈谈你对生产环境的经验?</b></summary><br>

待续

</details>

<details>
<summary><b><code>ls -al</code>输出中的各字段是什么意思?</b></summary><br>

按输出顺序来分别是:

```bash
-rwxrw-r--    1    root   root 2048    Jan 13 07:11 db.dump
```
- 文件权限,
- 链接数量,
- 文件所有者用户名,
- 文件所有者组名,
- 文件大小
- 最近修改的时间
- 文件/目录名

文件权限显示如下:

- 第一个字符是`-` 或 `l` 或 `d`,`d`表示是目录,`-`表示是文件,`l`表示是链接文件(或软链接) - 一种特殊的文件类型
- 三个字符一组,共三组,表示文件所有者,所有组和其他用户的权限:
  - r = 读权限
  - w = 写权限
  - x = 执行权限

例子中的`-rwxrw-r--`表示:

- 一个普通文件(`-`)
- 文件所有者可读,可写,可执行(`rwx`)
- 文件所有组可读,可写,不可执行(`rw-`)
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
- [What is/are the advantage(s) of running applications in backgound?](https://unix.stackexchange.com/questions/162186/what-is-are-the-advantages-of-running-applications-in-backgound)

一些其他的补充:
  
- **nohup**命令可以将程序以忽略挂起信号的方式运行起来:
```bash
nohup command >file 2>&1 &
```

- **screen**命令,详见[screen命令](http://man.linuxde.net/screen)

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

Linux负载平均值就是系统负载平均值,它将需要在系统上运行的线程(任务)显示为一个运行和等待的线程的平均值.这个需求量可以大于系统当前能处理的需求量.大多数工具显示了1,5,15分钟的平均值.

一些解读:

- 如果平均值是0.0,那么系统是空闲状态.
- 如果1分钟平均值大于5或15分钟平均值,那么负载在增加中.
- 如果1分钟平均值小于5或15分钟平均值,那么负载在减少中.
- 如果负载值大于cpu数量,那么可以会遇到性能问题(不一定).

参考文档:

- [Linux Load Averages: Solving the Mystery (original)](http://www.brendangregg.com/blog/2017-08-08/linux-load-averages.html)

</details>

<details>
<summary><b>Linux/UNIX中的密码文件在哪?</b></summary><br>
  
密码不存储在系统中的任何地方.**/etc/shadow** 中存储的是密码哈希后的值.

通过对文本(即密码)执行单向函数算法来创建出该文本的哈希值,从而创建出需要检查的字符串.这个被设计成"不可能"(计算力不够)逆转的过程.

较旧的UNIX版本会将加密后的密码和其他信息根据账户存储在 **/etc/passwd** 中.

新的则在 **/etc/passwd** 中的相关字段留一个`*`,并使用 **/etc/shadow** 来储存密码,来确保有人做不需要密码的操作时对密码没有读的权限(`shadow`的保护性比`passwd`更强).

更多信息查看`man crypt`, `man shadow`, `man passwd`.

参考文档:

- [Where is my password stored on Linux?](https://security.stackexchange.com/questions/37050/where-is-my-password-stored-on-linux)
- [Where are the passwords of the users located in Linux?](https://www.cyberciti.biz/faq/where-are-the-passwords-of-the-users-located-in-linux/)
- [Linux Password & Shadow File Formats](https://www.tldp.org/LDP/lame/LAME/linux-admin-made-easy/shadow-file-formats.html)

</details>

<details>
<summary><b>如何递归地修改除了文件的所有目录权限和除了目录的所有文件权限?</b></summary><br>
  
把所有目录改成755(drwxr-xr-x)权限:

`
find /opt/data -type d -exec chmod 755 {} \;
`<br><br>

把所有文件改成644 (-rw-r--r--)权限:<br>

`
find /opt/data -type f -exec chmod 644 {} \;
`<br><br>

参考文档:

- [How do I set chmod for a folder and all of its subfolders and files? (original)](https://stackoverflow.com/questions/3740152/how-do-i-set-chmod-for-a-folder-and-all-of-its-subfolders-and-files?rq=1)

</details>

<details>
<summary><b>执行命令报错<code>command not found</code>. 该如何查找原因和解决?</b></summary><br>

看起来可能是覆盖了默认的`PATH`环境变量.现有的错误类型表明`PATH`中没有包括 **/bin**,这个是命令(包括bash)所在的目录.

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

那么大多数命令都能工作 - 然后就可以编辑 **~/.bash_profile** (替代 **~/.bashrc**)来修复重置`PATH`.**root** 和其他用户的默认`PATH`变量在 **/etc/profile** 文件中.

参考文档:

- [How to correctly add a path to PATH?](https://unix.stackexchange.com/questions/26047/how-to-correctly-add-a-path-to-path)

</details>

<details>
<summary><b>输入<code>CTRL + C</code>后脚本还在继续运行. 该怎么停止?*</b></summary><br>

参考文档:

- [How to kill a script running in terminal, without closing terminal (Ctrl + C doesn't work)? (original)](https://askubuntu.com/questions/520107/how-to-kill-a-script-running-in-terminal-without-closing-terminal-ctrl-c-doe)
- [What's the difference between ^C and ^D for UNIX/Mac OS X terminal?](https://superuser.com/questions/169051/whats-the-difference-between-c-and-d-for-unix-mac-os-x-terminal)

</details>

<details>
<summary><b>grep命令是什么,如何在同一行中匹配多个字符串?</b></summary><br>
  
`grep`是Unix系列工具,还包括`egrep` and `fgrep`.

`grep`搜索文件模式.如果你要在另一个命令输出中匹配一个特定的模式,grep可以让相关行高亮.grep命令可以用来搜索日志文件,特定的进程等等.

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
- **SIGINT** - 当用户希望中断进程时通过控制终端发送SIGINT信号给进程.通常通过按下Ctrl+C发起,但在有些系统上,"delete"和"break"也有同样功能.
- **SIGKILL** - 当用户需要立刻终止进程时发送SIGKILL信号给进程(kill).与SIGTERM和SIGINT相反,该信号无法被捕捉或忽略,同时收到该信号的进程也无法执行任何清理操作.
- **SIGTERM** - 需要请求进程终止时发送SIGTERM信号给进程.和SIGKILL不同,它会被进程捕获,解析或忽略.SIGTERM信号可以让进程优雅地释放资源,保存状态然后终止.SIGTERM和SIGINT几乎相同.

参考文档:

- [POSIX signals](https://dsa.cs.tsinghua.edu.cn/oj/static/unix_signal.html)
- [Introduction To Unix Signals Programming](http://titania.ctie.monash.edu.au/signals/)

</details>

<details>
<summary><b><code>kill</code>命令的作用?</b></summary><br>

在Unix和类Unix操作系统中,kill是一个向进程发送信号的命令.默认发送的是终止信号,请求进程退出.但是kill算是一种误称,发送的信号不一定是终止信号.

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
<summary><b>如何列出archive.tgz的内容并提取一个文件?</b></summary><br>

```bash
tar tf archive.tgz
tar xf archive.tgz filename
```

参考文档:

- [List the contents of a tar or tar.gz file](https://www.cyberciti.biz/faq/list-the-contents-of-a-tar-or-targz-file/)
- [How to extract specific file(s) from tar.gz](https://unix.stackexchange.com/questions/61461/how-to-extract-specific-files-from-tar-gz)

</details>

<details>
<summary><b>如何同步2个本地目录?</b></summary><br>

在同一个系统上把dir1的内容同步到dir2中,输入:

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
- 最好使用`git`或其他版本控制工具来保持追踪配置文件(比如:`etckeeper` 用于 **/etc** 目录)

参考文档:

- [Backup file with .bak before filename extension](https://unix.stackexchange.com/questions/66376/backup-file-with-bak-before-filename-extension)
- [Is it a good idea to use git for configuration file version controlling?](https://superuser.com/questions/1037211/is-it-a-good-idea-to-use-git-for-configuration-file-version-controlling)

</details>

<details>
<summary><b>如何查找大于20m的文件?</b></summary><br>

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

它们在追查系统问题上是必不可少的,日志管理是IT安全的重要一部分.

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

- <b>RAID5</b>:一种通过计算奇偶校验数据来提高安全性,通过把数据分布在三个或更多驱动器的来提高速度(条带化)的磁盘系统.当单个驱动器发生故障时,可以读取计算分布式奇偶校验数据来恢复损坏盘中的数据.

- <b>RAID6</b>:RAID6通过新增一块奇偶校验盘来扩展RAID5.它至少需要4块磁盘,并能在2块盘同时发生故障时继续读写操作.RAID6对读操作没有性能损失,但由于计算奇偶校验的开销,在写操作上会有性能损失.

- <b>RAID10</b>:即RAID1+0,是一种结合了磁盘镜像化和磁盘条带化来保护数据的RAID配置.它至少需要4块盘,并把镜像的数据条带化.只要每对镜像化的磁盘中有一个正常工作,数据就可以恢复.但如果同一镜像对中的2块磁盘都发生了故障,那么由于条带化中没有奇偶校验,所有数据都会丢失.

参考文档:

- [RAID](https://www.prepressure.com/library/technology/raid)

</details>

<details>
<summary><b>如何指定和修改用户的默认组?</b></summary><br>

`useradd -m -g initial_group username`

<b>-g/--gid:</b>定义了用户初始登陆组的组名或组号.如果用这个参数指定了组名或组号,那组必须是已存在的.

如果没有使用该参数,那么将根据/etc/login.defs文件中的USERGROUPS_ENAB变量来决定useradd命令的结果.(USERGROUPS_ENAB yes)时默认创建一个与用户名相同的组,GID也等于UID.

参考文档:

- [How can I change a user's default group in Linux?](https://unix.stackexchange.com/questions/26675/how-can-i-change-a-users-default-group-in-linux)

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

###### 网络问题 (19)

<details>
<summary><b>按如下情况画出网络拓扑图:20个系统,1个路由器,4个交换机,5台服务器和一个小型IP防火墙?*</b></summary><br>

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

VLAN和子网解决不同的问题.VLAN在第二层工作,用来隔离广播域.而子网在第三层工作,用来隔离IP地址.

**Subnet** - 是一组通过部分地址(通常称为网络地址)和子网掩码(网络掩码)确定的IP地址范围.例如,如果网络掩码是255.255.255.0(或简写为/24),并且网络地址是192.168.10.0,那么就定义了从192.168.10.0到192.168.10.255范围的IP地址,可以简写为192.168.10.0/24.

**VLAN** - 可以理解为"交换分区".假设有一台支持VLAN的8端口交换机,你可以将其中4个端口分配给一个VLAN(如VLAN1),另外4个端口分配给另一个VLAN(如VLAN2).VLAN1看不到VLAN2上的任何流量,反之亦然.从逻辑上来说,现在有2个独立的交换机.通常当交换机找不到MAC地址时,会把流量"泛洪"到所有端口,VLAN可以防止这个.

子网只是用来帮助主机在二层和三层上通信的一个定义IP地址范围的IP地址.每个子网不需要专属的VLAN.而VLANS是用来实现隔离的(相当于在二层通信的沙箱,2个不同VLAN的系统之间可以通过VLAN路由来通信),为了方便管理和安全.

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
<summary><b><s>当你在浏览器中输入api.example.com并回车发生了什么?</s></b></summary><br>

首先,查询浏览器自己的DNS缓存,查不到时请求操作系统去解析域名.操作系统也有自己的DNS缓存,解析失败时再向操作系统配置的DNS服务器请求.操作系统配置的DNS服务器一般是由路由器中的DHCP服务配置的,而DHCP服务配置的基本上是从internet网关配置的ISP的DNS服务器.如果路由器有自己的DNS服务器,那一般也会有缓存,否则只要发现操作系统没有DNS缓存,就直接向ISP的DNS服务器请求解析.

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

这意味着,在某些系统上,可以绕过本地的hosts文件. **host.conf** 文件在Linux(和多数Unices)上可以控制这个.

如果你使用unix域套接字,速度会比TCP/IP稍快(系统开销小).Windows默认使用TCP/IP,而Linux根据你的选择来分,如果使用localhost,为unix域套接字,如果使用`127.0.0.1`,则是TCP/IP.

参考文档:

- **[What is the difference between 127.0.0.1 and localhost?](https://stackoverflow.com/questions/7382602/what-is-the-difference-between-127-0-0-1-and-localhost)**
- **[localhost vs. 127.0.0.1](https://stackoverflow.com/questions/3715925/localhost-vs-127-0-0-1)**

</details>

<details>
<summary><b><code>ping</code>命令使用了什么端口?</b></summary><br>

`ping`使用了ICMP协议,尤其是**ICMP echo request**和**ICMP echo reply**数据包,所以不存在所谓的端口.两个IP传输层协议,TCP和UDP,才用到端口.ICMP,TCP,UDP好比"兄弟姐妹",它们是独立的三个协议,运行在IP上.

ICMP数据包由IP数据报文头部的"协议"字段标识.ICMP不使用UDP或TCP通信服务,而是'raw'的IP通信服务.这表示IP数据报文的数据字段中直接携带了ICMP消息.('raw'表示在软件中实现创建和发送ICMP消息,打开'raw'套接字,构建包含ICMP消息的缓冲区,然后将包含信息的缓冲区写入'raw'套接字.)

ICMP的IP协议值为1.(协议字段是IP报文头的一部分,标识了该数据报文中的数据部分的内容.)

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

1.应用层:两台服务器上的服务是否正常运行?是否配置正确(比如绑定的IP和端口正确吗)?应用和系统日志是否有明显报错?

2.传输层:应用使用的端口是否打开(试试telnet)?服务器是否能ping通?

3.网络层:系统或网络上的防火墙是否配置正确?IP堆栈是否配置正确(IP,路由,DNS等)?交换机和路由器是否正常工作(检查ARP表!)?

4.物理层:服务器联网了吗?是否有丢包的现象?

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

查找IP地址WWW.XXX.YYY.ZZZ的主机名(注意八位字节是反转的), 或:

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
<summary><b>为什么要避免用telnet远程管理系统?</b></summary><br>

现在的操作系统默认关闭了所有有安全隐患的服务.另一方面,某些版本的网路设备仍然允许使用telnet协议建立通信.

telnet使用了很不安全的连接来通信.它用纯文本格式在网络上发送数据,任何人都可以用网络工具轻松找到密码.

对telnet来说,用纯文本格式来传递登陆凭证意味着在你的网路上运行嗅探器窃听telnet登陆会话的任何人都能在几秒钟找到关键信息来控制你的设备.

参考文档:

- [Telnet and SSH as a secure alternative](https://www.ssh.com/ssh/telnet)
- [How to telnet to an IP address on a specific port?](https://superuser.com/questions/339107/how-to-telnet-to-an-ip-address-on-a-specific-port)

</details>

<details>
<summary><b><code>wget</code>和<code>curl</code>之间有什么不同?</b></summary><br>
  
主要区别:wget可以以递归方式下载而curl不可以.wget只支持命令行,curl支持FTP,FTPS,HTTP,HTTPS,SCP,SFTP,TFTP,TELNET,DICT,LDAP,LDAPS,FILE,POP3,IMAP,SMTP,RTMP和RTSP.

参考文档:

- [What is the difference between curl and wget? (original)](https://unix.stackexchange.com/questions/47434/what-is-the-difference-between-curl-and-wget)

</details>

<details>
<summary><b>什么是SSH以及它是如何工作的?</b></summary><br>

SSH代表安全的shell.它是一种协议,允许你从通过服务器A跳转到服务器B的shell会话,然后和服务器B进行交互.

要建立一个SSH连接,需要远程服务器(B)运行ssh服务端进程并且用户的计算机(A)运行ssh客户端.

ssh服务端和客户端都监听一个特定的网络端口(默认是22),并对连接请求进行身份验证,当用户提供了正确的凭据时生成相应的工作环境.

参考文档:

- [Understanding the SSH Encryption and Connection Process](https://www.digitalocean.com/community/tutorials/understanding-the-ssh-encryption-and-connection-process)
  
</details>

<details>
<summary><b>什么是包过滤器以及它是如何工作的?</b></summary><br>  
  
包过滤器是一种防火墙技术,它控制网络访问的方式是:监控传入和传出的包并根据包中的源地址,目的地址,协议,端口等决定是否让包传递到系统网络或直接丢弃.
  
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

只是功能不同,设备是一样的

**默认网关**指的是你的LAN上的负责联络外部LAN流量的第一个连接点的路由地址.

参考文档:

- [Difference between router and gateway (orignal)](https://networkengineering.stackexchange.com/questions/51426/difference-between-router-and-gateway)

</details>

<details>
<summary><b>解释以下DNS的每个记录的功能:SOA, PTR, A, MX, 以及CNAME?</b></summary><br>      
  
DNS记录实质上是映射的文件,用来告诉DNS服务器每个域名和其对应的IP地址,以及如何处理发送给每个域名的请求.绝大部分DNS的记录配置使用以下记录类型:A, AAAA, CNAME, MX, PTR, NS, SOA, SRV, TXT, 和NAPTR.

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
<summary><b>可以用于最多30台设备的最小IPv4子网掩码是什么?</b></summary><br>      

最大30台设备的话是/27 - 或子网掩码`255.255.255.224`.

参考文档:

- [How do you calculate the prefix, network, subnet, and host numbers?](https://networkengineering.stackexchange.com/questions/7106/how-do-you-calculate-the-prefix-network-subnet-and-host-numbers)
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

###### Devops问题 (4)

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

当设备/程序/网络的配置方式可以被攻击者利用时,就是一种错误的安全配置.简单例子:使用默认的用户名/密码,简单的设备账户名等.

</details>

### :diamond_shape_with_a_dot_inside: 中级系统管理员

###### 系统问题 (50)

<details>
<summary><b>简述Linux启动流程.</b></summary><br>
  
**BIOS**:BIOS的全称为Basic Input or Output System,它先执行系统完整性检查,然后在MBR中查找并执行bootloader.

**Bootloader**:早期的操作系统,x86和x86-64架构被设计成当主引导记录(MBR)内的代码被执行了并加载了第一阶段的bootloader后启动基于BIOS的引导加载程序.在UEFI系统中,可以直接执行类似Linux内核的payload,因此不需要引导加载程序.常见的Bootloader有:**GRUB**,**Syslinux/Isolinux**或**Lilo**.

**MBR**:MBR全称为Master Boot Record,MBR记录了有关GRUB的信息,并执行和加载该GRUB.

**GRUB**:GRUB全称为Grand Unified Bootloader.如果系统上安装了多个内核镜像,那么需要选择加载哪个内核.

**Kernel**:Linux中的内核处理所有操作系统进程,比如内存管理,任务调度,I/O,进程间通信,和系统整体控制.内核(压缩镜像文件)被加载到内存中并解压缩,并设置一些基本功能,比如基本内存管理功能.

**Init**:它是系统上所有进程的父进程,有内核执行,用来启动其他进程.

- `SysV init` - init的工作是"在内核完全启动时让所有程序按要求运行".根据设定的默认运行级别,系统执行对应的程序.实际上是它建立并操作了整个用户空间,包括检查和挂载文件系统,启动必要的用户服务,并在系统启动完成后切换到用户环境.

- `systemd` - systemd被开发用于取代目前从UNIX中继承的System V这个Linux init系统.
类似init,systemd也是一个管理其他守护进程的守护进程.所有守护进程(包括systemd)都是后台进程.Systemd是第一个启动(开机时)和最后一个停止(关机时)的守护进程.

- `runint` - runint是类UNIX操作系统的初始化进程,用于初始化,监控和停止所有操作系统上的进程.它是在Linux,Mac OS X,*BSD,和Solaris操作系统上运行的进程监控组件的重写.

**Runlevel programs**:根据设定的默认运行级别,系统执行对应的程序.

参考文档:

- [Analyzing the Linux boot process](https://opensource.com/article/18/1/analyzing-linux-boot-process)
- [Systemd Boot Process a Close Look in Linux](https://linoxide.com/linux-how-to/systemd-boot-process/)

</details>

<details>
<summary><b><s>什么是UID为0叫`toor`的账户?是被入侵了吗?</s></b></summary><br>

`toor`是一个超级账户root的"替代",由root反着拼写而来.它可以在非标准的shell上使用,所以root就能在默认的shell上直接使用.

因为shells不是基础发行版的一部分,而是通过端口或安装包默认安装在不同的文件系统中
  
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

实际用户ID是你启动进程的用户,有效用户ID是由操作系统来决定你是否被允许执行某些操作(大多数情况下,偶有例外).

当你登陆后,shell通过password文件同时把实际和有效用户ID设定为同一值.

比如,你执行了setuid(一个函数),并且没有用其他(例如root)用户运行,那么setuid程序做了以下操作:

setuid会获取你的实际id(基于你是程序所有者)和文件所有者的有效用户(例如root).

当passw的权限如下:

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

处理日志文件可以使用`logrotate`.不过应该在将任务添加在 **/etc/logrotate.d/** 中而不是直接在 **/etc/logrotate.conf** 中修改.不然当有版本升级时就会有很多配置文件差异了.

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
<summary><b>Linux内核如何创建,管理和删除系统中的进程?</b></summary><br>

待续

参考文档:

- [Linux Processes](https://www.tldp.org/LDP/tlk/kernel/processes.html)

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
<summary><b>当服务器启动时在console中报错了,该如何找到这些信息并检查?</b></summary><br>

console中有2种类型的信息:

- **由内核生成** (通过printk)
- **由用户空间生成** (通常是操作系统)

内核信息总是存储在**kmsg**缓冲区中,可以通过`dmesg`命令查看,也常被复制到**syslog**中.用户空间信息也会被写入`/dev/kmsg`中,不过非常少见.

与此同时,当用户空间将它花哨的启动状态信息写入`/dev/console`或`/dev/tty1`中时,它仅仅是显示在屏幕上而不存储在任何地方.

