---
title: linux命令执行顺序控制与管道
tags: linux
categories: linux
---


# 命令执行顺序的控制
## 顺序执行多条命令

eg:
```
#更新软件源里的软件列表
$ sudo apt-get update
$ sudo apt-get install some-tool //这里some-tool是指具体的软件包，例如：banner
$ some-tool
```

## 有选择的执行命令
eg:
```
$ which cowsay>/dev/null && cowsay -f head-in ohch~
```

你如果没有安装cowsay，你可以先执行一次上述命令，你会发现什么也没发生，你再安装好之后你再执行一次上述命令，你也会发现一些惊喜。

上面的&&就是用来实现选择性执行的，它表示如果前面的命令执行结果（不是表示终端输出的内容，而是表示命令执行状态的结果）返回0则执行后面的，否则不执行，你可以从$?环境变量获取上一次命令的返回结果：

![](https://doc.shiyanlou.com/document-uid1labid63timestamp1544148440172.png/wm)

||就是与&&相反的控制效果，当上一条命令执行结果为≠0($?≠0)时则执行它后面的命令：
```
$ which cowsay>/dev/null || echo "cowsay has not been install, please run 'sudo apt-get install cowsay' to install"
```

流程图：

![](https://doc.shiyanlou.com/linux_base/8-3.png/wm)

# 管道
管道是什么？管道是一种通信机制，通常用于进程间的通信（也可通过socket进行网络通信），它表现出来的形式就是将前面每一个进程的输出(stdout)直接作为下一个进程的输入(stdin)。

管道又分为匿名管道和具名管道，在使用一些过滤程序时经常会用到的就是匿名管道，在命令行中由`|`分隔符表示,具名管道简单的说就是有名字的管道，通常只会在源程序中用到具名管道。


先试用一下管道，比如查看/etc目录下有哪些文件和目录，使用ls命令来查看：
```
$ ls -al /etc
```
有太多内容，屏幕不能完全显示，这时候可以使用滚动条或快捷键滚动窗口来查看。不过这时候可以使用管道：
```
$ ls -al /etc | less
```
通过管道将前一个命令(ls)的输出作为下一个命令(less)的输入，然后就可以一行一行地看。

## cut 命令，打印每一行的某一字段

打印/etc/passwd文件中以:为分隔符的第1个字段和第6个字段分别表示用户名和其家目录：
```
$ cut /etc/passwd -d ':' -f 1,6
```
打印/etc/passwd文件中每一行的前N个字符：
```
# 前五个（包含第五个）
$ cut /etc/passwd -c -5
# 前五个之后的（包含第五个）
$ cut /etc/passwd -c 5-
# 第五个
$ cut /etc/passwd -c 5
# 2到5之间的（包含第五个）
$ cut /etc/passwd -c 2-5
```

## grep 命令，在文本中或 stdin 中查找匹配字符串

grep命令的一般形式为：
```
grep [命令选项]... 用于匹配的表达式 [文件]...

```

搜索/home/shiyanlou目录下所有包含"shiyanlou"的文本文件，并显示出现在文本中的行号：
```
$ grep -rnI "shiyanlou" ~
```

- -r 参数表示递归搜索子目录中的文件
- -n表示打印匹配项行号
- -I表示忽略二进制文件

当然也可以在匹配字段中使用正则表达式，下面简单的演示：

```
# 查看环境变量中以"yanlou"结尾的字符串
$ export | grep ".*yanlou$"
```

- $表示一行的末尾

## wc 命令，简单小巧的计数工具

wc 命令用于统计并输出一个文件中行、单词和字节的数目，比如输出/etc/passwd文件的统计信息：
```
$ wc /etc/passwd
```
分别只输出行数、单词数、字节数、字符数和输入文本中最长一行的字节数：
```
# 行数
$ wc -l /etc/passwd
# 单词数
$ wc -w /etc/passwd
# 字节数
$ wc -c /etc/passwd
# 字符数
$ wc -m /etc/passwd
# 最长行字节数
$ wc -L /etc/passwd
```

##  sort 排序命令
这个命令前面我们也是用过多次，功能很简单就是将输入按照一定方式排序，然后再输出,它支持的排序有按字典排序,数字排序，按月份排序，随机排序，反转排序，指定特定字段进行排序等等。

默认为字典排序：
```
$ cat /etc/passwd | sort
```
反转排序：
```
$ cat /etc/passwd | sort -r
```
按特定字段排序：
```
$ cat /etc/passwd | sort -t':' -k 3
```
- -t参数用于指定字段的分隔符，这里是以":"作为分隔符；
- -k 字段号用于指定对哪一个字段进行排序。

这里/etc/passwd文件的第三个字段为数字，默认情况下是以字典序排序的，如果要按照数字排序就要加上-n参数：
```
$ cat /etc/passwd | sort -t':' -k 3 -n
```

## uniq 去重命令

uniq命令可以用于过滤或者输出重复行。

###  过滤重复行

我们可以使用history命令查看最近执行过的命令（实际为读取${SHELL}_history文件,如我们环境中的~/.zsh_history文件），不过你可能只想查看使用了哪个命令而不需要知道具体干了什么，那么你可能就会要想去掉命令后面的参数然后去掉重复的命令：
```
$ history | cut -c 8- | cut -d ' ' -f 1 | uniq
```
然后经过层层过滤，你会发现确是只输出了执行的命令那一列，不过去重效果好像不明显，仔细看你会发现它确实去重了，只是不那么明显，之所以不明显是因为uniq命令只能去连续重复的行，不是全文去重，所以要达到预期效果，我们先排序：
```
$ history | cut -c 8- | cut -d ' ' -f 1 | sort | uniq
# 或者$ history | cut -c 8- | cut -d ' ' -f 1 | sort -u
```
这就是 Linux/UNIX 哲学吸引人的地方，大繁至简，一个命令只干一件事却能干到最好。

### 输出重复行
```
# 输出重复过的行（重复的只输出一个）及重复次数
$ history | cut -c 8- | cut -d ' ' -f 1 | sort | uniq -dc
# 输出所有重复的行
$ history | cut -c 8- | cut -d ' ' -f 1 | sort | uniq -D
```