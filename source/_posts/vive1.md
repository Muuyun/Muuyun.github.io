---
title: HTC VIVE - 1
tags: vr
categories: technology
---

安装VIVE和SteamVR至少需要占用1020MB的磁盘空间。

## 技术规格

“HTC Vive”具有90赫兹的刷新速率。该设备使用两个屏幕，每眼一个屏幕，每个屏幕具有1080×1200分辨率。

最低系统要求
```
    GPU: NVIDIA GeForce GTX 970 / AMD Radeon R9 290 同等或更高的版本
    CPU: Intel i5-4590 / AMD FX-8350 同等或更高的版本
    RAM: 4GB+
    Video Output: HDMI 1.4 或 DisplayPort 1.2 或更高版本
    USB Port: 1x USB 2.0 或更高版本
    操作系统: Windows 7 SP1 或更新版本[8]
```


## Viveport M简介

Viveport M是HTC面向移动市场推出的虚拟现实应用商店，适用于Android平台并广泛兼容多种移动VR设备，其内容将以360°视频和体验类游戏为主，旨在为用户提供更多元化、更高品质的移动VR内容与体验。Viveport M将为全球数以万计的开发者提供一个展示内容的新平台，吸引更多开发者和合作伙伴加入到蓬勃发展的Vive生态系统中，接触到全球增长速度最快的用户群体。
系统支持：安卓5.0及以上；屏幕尺寸：5-6寸

## 手柄

1 开关、系统菜单按钮：只有这个按钮不可以编程（默认），用来打开手柄，其实没用关的功能。在游戏中按下该按钮是调出系统默认的菜单，用来关闭，切换游戏用的。

2 menu按钮：默认用来打开游戏菜单。

3 grip按钮：用的最少的按钮，每个手柄上虽然有两个，但是是相同的。

4 trigger按钮：扳机按钮，用的最多，可以有力度。

5 pad：触摸屏+鼠标的功能，可触摸，可点击。

## vive开发

需要两个插件：

[SteamVR Plugin](https://www.assetstore.Unity3D.com/cn/#!/content/32647)

[Vive Input Utility](https://www.assetstore.unity3d.com/cn/#!/content/64219)
```
SteamVR 

这个目录下的脚本都是用来定制SteamVR插件中某些脚本在Unity中的Inspector界面及功能的
——Editor

    定制SteamVR_Camera.cs这个脚本在Inspector中的显示效果 
    SteamVR_Editor.cs  
    定制SteamVR_RenderModel.cs脚本在Inspector中的功能 
    SteamVR_RenderModelEditor.cs　 
    上面提到的弹出的SteamVR_Settings对话框里面的选项就在这儿定制 
    SteamVR_Settings.cs　　　　　　 
    定制SteamVR_SkyBox.cs在Inspector中显示的属性
    SteamVR_SkyboxEditor.cs　　　　 
    用来检查插件的更新　　 
    SteamVR_Update.cs　　
　　　　　 
这个文件夹下面放着一些工具脚本　　　　　 
——Extras　　　　 

    这个脚本用来检测物体是否被用户所凝视　　　　
    SteamVR_GazeTracker.cs 　　　　 
    通过手柄指向来产生一条激光束 
    SteamVR_LeaserPointer.cs　　　　
    用来瞬移的脚本 
    SteamVR_Teleporter.cs　　　　　 
    示例场景中扔物体的脚本
    SteamVR_TestThrow.cs　　　　　　
    示例场景中跟踪相机的脚本 
    SteamVR_TestTrackedCamera.cs　 
    控制器(手柄)集成脚本
    SteamVR_trackedController.cs　 

存放示例demo的材质体　　 
——Materials 
存放SteamVR预制体
——Prefabs 

    相机预制体　 
    [CameraRig] 
    状态相关的overlay显示预制体　 
    [Status] 
    /*SteamVR_Render预制体*/　 
    [SteamVR] 

/*一些自带的shader*/　 
——Scenes
/*SteamVR核心脚本*/　 
——Scripts 
    /*SteamVR的封装类*/ 
    SteamVR.cs 
    /*SteamVR的核心相机类*/ 
    SteamVR_Camera.cs 
    /*SteamVR相机翻转*/ 
    SteamVR_CameraFlip.cs 
    /*SteamVR相机网格隐藏*/ 
    SteamVR_CameraMask.cs 
    /*控制器封装类*/ 
    SteamVR_Controller.cs 
    /*控制器管理类*/ 
    SteamVR_ControllerManager.cs 
    /*声音控制类*/ 
    SteamVR_Ears.cs 
    /*外部相机*/ 
    SteamVR_ExternalCamera.cs 
    /*场景进行渐显或者渐隐的类*/ 
    SteamVR_Fade.cs 
    /*跟踪设备的扫描范围*/ 
    SteamVR_Frustum.cs 
    /*绘制pc上的伴随窗口*/ 
    SteamVR_GameView.cs 
    /*关节反身运动*/ 
    SteamVR_IK.cs 
    /*场景切换类*/ 
    SteamVR_LoadLevel.cs 
    /*菜单类*/ 
    SteamVR_Menu.cs 
    /*overly封装类*/ 
    SteamVR_Overlay.cs 
    /*运动区域*/ 
    SteamVR_PlayArea.cs 
    /*Vive渲染流程控制的核心类*/ 
    SteamVR_Render.cs 
    /*设置天空盒*/ 
    SteamVR_Skybox.cs 
    /*做球形投影的类*/ 
    SteamVR_SphericalProjection.cs 
    /*通过overlay显示统计信息*/ 
    SteamVR_Stats.cs 
    /*根据不同状态渐变显示不同的信息*/ 
    SteamVR_Status.cs 
    /*根据不同状态渐变显示不同文本信息*/ 
    SteamVR_StatusText.cs 
    /*控制器测试脚本*/ 
    SteamVR_TestController.cs 
    /*头盔上的前置相机*/ 
    SteamVR_TrackedCamera.cs 
    /*跟踪设备管理类*/ 
    SteamVR_TrackedObject.cs 
    /*5.x版本以前更新设备位置的脚本*/ 
    SteamVR_UpdatePoses.cs 
    /*工具类，包括事件系统，Transform等等*/ 
    SteamVR_Utils.cs 
    
/*常用的纹理*/ 
——Textures
```

