---
title: 文件系统操作与磁盘管理
tags: linux
categories: linux
---

# 查看磁盘和目录的容量

> 使用df命令查看磁盘的容量
```
$ df
$ df -h
```

> 使用du命令查看目录的容量

```
# 默认同样以 块 的大小展示
$ du
# 加上-h参数，以更易读的方式展示
$ du -h
```

`-d` 参数指定查看目录的深度
```
# 只查看1级目录的信息
$ du -h -d 0 ~
# 查看2级
$ du -h -d 1 ~
```
常用参数
```
du -h #同--human-readable 以K，M，G为单位，提高信息的可读性。
du -a #同--all 显示目录中所有文件的大小。
du -s #同--summarize 仅显示总计，只列出最后加总的值。
```

# 创建虚拟磁盘
> 用dd命令从标准输入读入用户的输入到标准输出或者一个文件中：

```
# 输出到文件
$ dd of=test bs=10 count=1
# 输出到标准输出
$ dd if=/dev/stdin of=/dev/stdout bs=10 count=1
# 注:在打完了这个命令后，继续在终端打字，作为你的输入
```
- bs（block size）用于指定块大小（缺省单位为 Byte，也可为其指定如'K'，'M'，'G'等单位），count用于指定块数量。

> 将输出的英文字符转换为大写再写入文件：
```
$ dd if=/dev/stdin of=test bs=10 count=1 conv=ucase
```

## 使用 dd 命令创建虚拟镜像文件
> 从/dev/zero设备创建一个容量为 256M 的空文件：
```
$ dd if=/dev/zero of=virtual.img bs=1M count=256
$ du -h virtual.img
```

## 使用 mkfs 命令格式化磁盘（我们这里是自己创建的虚拟磁盘镜像）
> $ sudo mkfs.ext4 virtual.img

## 使用 mount 命令挂载磁盘到目录树
- mount命令的一般格式如下：
```
mount [options] [source] [directory]
```
- 一些常用操作：
```
mount [-o [操作选项]] [-t 文件系统类型] [-w|--rw|--ro] [文件系统源] [挂载点]
```


