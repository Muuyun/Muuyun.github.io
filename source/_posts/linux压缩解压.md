---
title: linux压缩解压工具
tags: linux
categories: linux
---

# 压缩文件
linux常见格式：`.zip`,`.rar`,`.7z`,`.tar`,`.gz`,`.xz`,`.bz2`,`.tar.gz`,`.tar.xz`,`tar.bz2`,`.tar.7z`

## zip压缩打包程序

### 使用zip打包文件夹
```
$ cd /home/shiyanlou
$ zip -r -q -o shiyanlou.zip /home/shiyanlou/Desktop
$ du -h shiyanlou.zip
$ file shiyanlou.zip
```
- -r 参数表示递归打包包含子目录的全部内容，
- -q 参数表示为安静模式，即不向屏幕输出信息，
- -o，表示输出文件，需在其后紧跟打包输出文件名。
- du ,命令查看打包后文件的大小

### 设置压缩级别为9和1（9最大，1最小），重新打包：
```
$ zip -r -9 -q -o shiyanlou_9.zip /home/shiyanlou/Desktop -x ~/*.zip
$ zip -r -1 -q -o shiyanlou_1.zip /home/shiyanlou/Desktop -x ~/*.zip
```
- -[1-9] 表示压缩级别，1 表示最快压缩但体积大，9 表示体积最小但耗时最久。
- -x 是为了排除我们上一次创建的 zip 文件，否则又会被打包进这一次的压缩文件中，**注意：这里只能使用绝对路径，否则不起作用。**

### 创建加密 zip 包
使用 -e 参数可以创建加密压缩包：
```
$ zip -r -e -o shiyanlou_encryption.zip /home/shiyanlou/Desktop
```

**如果你想让你在 Linux 创建的 zip 压缩文件在 Windows 上解压后没有任何问题,需要加上 `-l `参数将` LF` 转换为 `CR+LF`**
```
$ zip -r -l -o shiyanlou.zip /home/shiyanlou/Desktop
```


## 使用 unzip 命令解压缩 zip 文件
将 shiyanlou.zip 解压到当前目录：
```
$ unzip shiyanlou.zip
```
使用安静模式，将文件解压到指定目录：
```
$ unzip -q shiyanlou.zip -d ziptest
```
如果你不想解压只想查看压缩包的内容你可以使用 -l 参数：
```
$ unzip -l shiyanlou.zip
```
**通常 Windows 系统上面创建的中文名压缩文件，默认会采用 GBK 编码，而 Linux 上面默认使用的是 UTF-8 编码，如果不加任何处理，直接解压的话可能会出现中文乱码的问题**
```
unzip -O GBK 中文压缩文件.zip
```

## tar打包工具
> 创建一个 tar 包：
```
$ cd /home/shiyanlou
$ tar -cf shiyanlou.tar /home/shiyanlou/Desktop
```
- -c 表示创建一个 tar 包文件
- -f 用于指定创建的文件名
- -v 以可视的的方式输出打包的文件

> 解包一个文件（-x 参数）到指定路径的已存在目录（-C 参数）：

```
$ mkdir tardir
$ tar -xf shiyanlou.tar -C tardir
```

> 只查看不解包文件 -t 参数：
```
$ tar -tf shiyanlou.tar
```

> 在创建 tar 文件的基础上添加 -z 参数，使用 gzip 来压缩文件：

```
$ tar -czf shiyanlou.tar.gz /home/shiyanlou/Desktop
```

> 解压 *.tar.gz 文件：
```
$ tar -xzf shiyanlou.tar.gz
```

## 常用命令
zip：

    打包 ：zip something.zip something （目录请加 -r 参数）
    解包：unzip something.zip
    指定路径：-d 参数

tar：

    打包：tar -cf something.tar something
    解包：tar -xf something.tar
    指定路径：-C 参数

