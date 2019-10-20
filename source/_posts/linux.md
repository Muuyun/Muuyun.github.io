---
title: Linux-basics
tags: linux
categories: linux
---
## Linux的几个优点：

  1. 免费
  2. 很多软件原生是在Linux下运行的，庞大的社区支持，生态环境好。
  3. 开源，可被定制，开放，多用户的网络操作系统。
  4. 相对安全稳定

> sh ss.sh
>
> vim /etc/zsh/zshrc
>
> / 78 , boot  2 , home 40 , swap 2 ,  ubuntu 120   

##  Linux 基本目录结构

-  bin 存放二进制可执行文件(ls,cat,mkdir等) 
-  boot 存放用于系统引导时使用的各种文件 
-  dev 用于存放设备文件 
-  etc 存放系统配置文件 
-  home 存放所有用户文件的根目录 
-  lib 存放跟文件系统中的程序运行所需要的共享库及内核模块 
-  mnt 系统管理员安装临时文件系统的安装点 
-  opt 额外安装的可选应用程序包所放置的位置 
-  proc 虚拟文件系统，存放当前内存的映射 
-  root 超级用户目录 
-  sbin 存放二进制可执行文件，只有root才能访问 
-  tmp 用于存放各种临时文件 
-  usr 用于存放系统应用程序，比较重要的目录/usr/local 本地管理员软件安装目录 
-  var 用于存放运行时需要改变数据的文件

## 趣谈Linux

初创期：这个老板基于开放的营商环境（**x86 体系结构**），创办一家外包公司（**系统的启动**）。因为一开始没有其他员工，老板需要亲自接项目（**实模式**）。
发展期：公司慢慢做大，项目越接越多（**保护模式、多进程**），为了管理各个外包项目，建立 了项目管理体系（**进程管理**）、会议室管理体系（**内存管理**）、文档资料管理系统（**文件系统**）、售前售后体系（**输入输出设备管理**）。
壮大期：公司越来越牛，开始促进内部项目的合作（**进程间通信**）和外部公司合作（**网络通信**）。
  最新一手资源 更新通知 加微信 ixuexi66 资料整理不易 仅供个人学习 请勿倒卖 
集团化：公司的业务越来越多，会成立多家子公司（**虚拟化**），或者鼓励内部创业（**容器化**），这个时候公司就变成了集团。大管家的调度能力不再局限于一家公司，而是集团公司 （**Linux 集群**），从而成功上市（**从单机操作系统到数据中心操作系统**）。

![UTOOLS1569749305586.png](https://i.loli.net/2019/09/29/Pj5fhGKT4YoaLSN.png)
![UTOOLS1569749328489.png](https://i.loli.net/2019/09/29/mLDYKlehcGqJnW4.png)
![UTOOLS1569749363899.png](https://i.loli.net/2019/09/29/XUkhfQdwqvmjz6r.png)
![UTOOLS1569749407501.png](https://i.loli.net/2019/09/29/XPnbrouNCVcOQwJ.png)
![UTOOLS1569749428851.png](https://i.loli.net/2019/09/29/M97ClQzrkfWHeKL.png)
![UTOOLS1569749463343.png](https://i.loli.net/2019/09/29/CJPL32Smpr7e9qQ.png)
![UTOOLS1569749485031.png](https://i.loli.net/2019/09/29/nAUqMcNIEOif2Ds.png)

## 关于linux的不错的文章

1. [Linux指令学习笔记](https://www.vincentqin.tech/posts/Linux-commands/)
2. [目录文件权限的查看和修改](https://www.cnblogs.com/sxdcgaq8080/p/7498906.html)
3. [看完这篇Linux的基本操作就会了](https://www.jianshu.com/p/a182a0be4b8a)



