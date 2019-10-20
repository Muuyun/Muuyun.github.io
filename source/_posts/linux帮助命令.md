---
title: linux帮助命令和crontab
tags: linux
categories: linux
---

## 内建命令与外部命令
可以用type来区分命令是内建的还是外部的
```
type + 命令
```
- 内建命令是写在bash源码的builtins里面的
- 外部命令通常放在/bin，/user/bin,/sbin,/usr/sbin等等

## crontab语法
用于设置周期性被执行的指令。通常，crontab 储存的指令被守护进程激活，crond 为其守护进程，crond 常常在后台运行，每一分钟会检查一次是否有预定的作业需要执行。

通过 crontab 命令，我们可以在固定的间隔时间执行指定的系统指令或 shell　script 脚本。时间间隔的单位可以是分钟、小时、日、月、周的任意组合。

crontab 的格式:
```
# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name command to be executed
```

```
$ crontab -e 表示为当前用户添加计划任务
$ sudo crontab -e 表示为root用户添加计划任务
```