---
title: linux环境变量
tags: linux
categories: linux
---

# 变量

```
$ declare tmp
```

> 使用 declare 命令创建一个变量名为 tmp 的变量

```
$ echo $tmp
```

> 读取变量的值

```
zsh
```

> 创建子shell

```
export temp
```

> 导出变量temp为环境变量

```
gedit hello_shell.sh
```

> 创建一个shell脚本文件，第一行  `#!/bin/bash` 不能省略

```
$ PATH=$PATH:/home/shiyanlou/mybin
```

> 添加环境变量，可以在任意目录执行mybin里面的文件

```
$ echo "PATH=$PATH:/home/shiyanlou/mybin" >> .zshrc
```

> 让添加的变量全局有效
 - `>>` 表示将标准输出以追加的方式重定向到一个文件中
 - `>` 是以覆盖的方式重定向到一个文件中

```
source .zshrc
```

> 让环境变量立即生效

```
unset temp
```

> 删除一个环境变量

# 环境变量
![](https://doc.shiyanlou.com/linux_base/5-2.png/wm)

## 变量类型：
- 用户自定义变量
- Shell本身内建的变量
- 从自定义变量导出的环境变量

|命 令    |说 明                                                                 |
|--------|:--------------------------------------------------------------------:|
|set     |显示 Shell 所有变量，包括其内建环境变量，用户自定义变量及导出的环境变量。   |
|env 	 |显示与当前用户相关的环境变量，还可以让命令在指定环境中运行。                |
|export  |显示从 Shell 中导出成环境变量的变量，也能通过它将自定义变量导出为环境变量。  |




按变量的生存周期来划分，Linux 变量可分为两类：

- 永久的：需要修改配置文件，变量永久生效；

- 临时的：使用 export 命令行声明即可，变量在关闭 shell 时失效。

```
/etc/bashrc
```

> 存放shell变量

```
/etc/profile
```

> 存放环境变量

# 搜索文件
与搜索相关的命令常用的有 `whereis，which，find `和 `locate `。




