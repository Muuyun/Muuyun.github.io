---
title: wechat applet

tags: wechat applet

categories: technology

---



# 微信小程序的视图与渲染

1. 组件的基本使用
2. 数据绑定 
3. 渲染标签: 判断标签，循环标签
4. 模板的使用：include，import



# 微信小程序的事件——课程概要

1. 什么是事件

   一种用户行为，一种通讯方式

2. 事件类别

   - 点击事件tap
   - 长按事件 longtan
   - 触摸事件 touchstart touchend touchmove touchcancel
   - 其他 submit input…

3. 事件冒泡

   - 冒泡事件
   - 非冒泡事件

4. 事件绑定

   - bind
   - catch : 不会触发父view

5. 事件对象详解

   - 类型type
   - 时间戳 timeStamp
   - 事件源组件 target
   - 当前组件 currentTarget
   - 触摸点数 touches

# 综合案例一快递查询

1. 产品需求
2. 准备
3. 编码实战

# 微信小程序的配置详解

1. app的页面配置
2. app的窗口配置
3. app的 tabBar配置
4. 网络超时配置及 debug开启配置
5. 页面配置

# 微信小程序的生命周期与app对象的使用

1. APP的生命周期
2. APP对象的使用

# 微信小程序页面的生命周期和参数传递

1. 页面的生命周期
2. 页面跳转的数据传递 wx: navigateTo / wx: redirectTo

# 综合案例——用户登录

1. 项目需求
2. 编码实战

# 微信小程序的UI精讲

1. 布局和样式基础
2. 组件使用
3. 项目实战



# 微信小程序UI精讲之布局基础

1. flex布局基础

   - flex的容器和元素
   - flex容器属性详解
     - flex- direction决定元素的排列方向
     - flex-wrap决定元素如何换行(排列不下时)
     - flex-flow flex- direction和fex-wrap的简写
     - justify- content元素在主轴上的对齐方式
     - align-items元素在交叉轴的对齐方式
   - flex元素属性详解
     - flex-grow当有多余空间时,元素的放大比例
     - flex-shrink当空间不足时,元素的缩小比例
     - flex- basis元素在主轴上占据的空间
     - flex是grow、 shrink、 basis的简写
     - order定义元素的排列顺序
     - align-self定义元素自身的对齐方式
   - flex布局实战

2. 相对定位和绝对定位

   1. 理解相对定位和绝对定位

   2. 相对定位、绝对定位的编码实战

相对定位的元素是相对**自身**进行定位,参照物是**自己**。
绝对定位的元素是相对**离它最近的一个已定位的父级元素**进行定位。

# 微信小程序UI精讲之组件的使用

1. 组件的使用
2. 组件的配置

# 微信小程序精讲之视图容器组件

- view
- scroll-view
- swiper

# 微信小程序UI精讲之基础内容组件

- Icon
- text
- progress

# 微信小程序UI精讲之表单组件

- button          按钮
- checkbox    多选框
- Input             输入框
- label              标签
- picker           选择器
- radio             单选框
- slide              滑块
- switch          开关
- form             表单

# 微信小程序UI精讲之操作反馈小工具

- action-sheet
- modal
- toast
- loading

# 微信小程序UI精讲之导航

- navigator

# 微信小程序UI精讲之多媒体

- image
- audio
- video

# 微信小程序UI精讲之地图与LBS

- 地图map的基本使用
- 地图标记
- 地图覆盖物

# 微信小程序UI精讲之画布与游戏

- canvas的使用
- 绘图API的使用

# 综合案例-评测小程序首页的实现

- 项目需求
- 编码实战

# 微信小程序API之请求服务器数据

- wx.request的使用
- 了解http协议

# 微信小程序API之图片选择与调用微信拍照

- wx. chooselmage选择图片
- 照相机拍照

# 微信小程序API之文件上传与下载

- 文件上传
- 文件下载

# 微信小程序API之 WebSocket精讲

- 什么是 WebSocket
- 使用 WebSocket
- 监听 WebSocket

# 微信小程序API之音乐的播放和控制



- 音乐的播放
- 音乐的控制

# 微信小程序API之缓存数据



- 保存数据
- 读取数据
- 删除数据
- 数据异步操作

# 微信小程序API之获取当前位置

- 获取位置
- 查看位置

# 微信小程序API之设备信息

- 网络状态
- 获取系统信息
- 获取重力感应
- 罗盘
- 拔打电话

# 微信小程序API之交互反馈

- showToast
- showModal
- showActionSheet

# 微信小程序API之导航和导航条

- 导航条标题设置
- 导航条加载动画设置
- 导航

# 微信小程序API之动画

- 动画的基本使用
- 旋转动画
- 缩放动画
- 偏移动画
- 倾斜动画
- 矩阵变形

# 微信小程序API之绘图

- cavans及context详解
- 绘图API的使用
- 游戏的制作

# 课程介绍

课程安排

1. 产品设计-进行产品分析(xmind)和原型设计(墨刀)

2. 框架搭建-微信小程序MINA框架讲解和配置

   ![UTOOLS1570885215652.png](https://i.loli.net/2019/10/12/cRB8tCwla9xTN6W.png)

   ![UTOOLS1570885242529.png](https://i.loli.net/2019/10/12/DWVIjBN6R1YtbzO.png)

# 产品层级、组件模块化设计

- 为什么要对小程序进行组件模块化设计?
  微信小程序有代码大小限制
  提高代码的复用率
- 如何进行组件模块化设计?
  通过WXML的import和 include来使用文件模板
  使用WXSS的@import来引用WXSS文件
  使用JS的 require来引用JS文件



---

1. `.json` 后缀的 `JSON` 配置文件
2. `.wxml` 后缀的 `WXML` 模板文件
3. `.wxss` 后缀的 `WXSS` 样式文件
4. `.js` 后缀的 `JS` 脚本逻辑文件
5. `pages`字段 —— 用于描述当前小程序所有页面路径，这是为了让微信客户端知道当前你的小程序页面定义在哪个目录。
6. `window`字段 —— 定义小程序所有页面的顶部背景颜色，文字颜色定义等。





- 从事过网页编程的人知道，网页编程采用的是 HTML + CSS + JS 这样的组合，其中 `HTML` 是用来描述当前这个页面的结构，`CSS` 用来描述页面的样子，`JS` 通常是用来处理这个页面和用户的交互。

  同样道理，在小程序中也有同样的角色，其中 `WXML` 充当的就是类似 `HTML` 的角色。
  `WXSS` 具有 `CSS` 大部分的特性，小程序在 `WXSS` 也做了一些扩充和修改。



- 1rpx = 0.5px = 1物理像素。

  小程序编译后，rpx会做一次px换算。换算是以375个物理像素为基准，也就是在一个宽度为375物理像素的屏幕下，1rpx = 1px。

  举个例子：iPhone6屏幕宽度为375px，共750个物理像素，那么1rpx = 375 / 750 px = 0.5px。



- 还需要注意的是 JSON 文件中无法使用注释，试图添加注释将会引发报错。



- “比如我在面试的时候问到一个关于小程序的问题，问小程序有window对象吗？他说有吧”，但其实是没有的。



























