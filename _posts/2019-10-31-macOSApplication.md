---
layout:     post
title:      "Mac应用程序无法打开或文件损坏的处理方法"
subtitle:   "安装第三方源App"
date:       2019-10-31 22:00:00
author:     "Tickmao"
header-style: "text"
catalog:     true
tags:
    - macOS Catalina
    - Mac
    - 程序安装
    - 损坏
    - 第三方App
---

Mac用户在升级到最新系统macOS Catalina后，当安装 Mac 应用时，经常会遇到提示 “ XXX.app 已损坏，打不开。您应该将它移到废纸篓 ” 或 “ 打不开 XXX.app，因为它来自身份不明的开发者 ”

遇到这种办法，需要对系统权限进行调整

### 开启任何来源

1.打开终端（Terminal.app）

2.输入以下命令 sudo spctl --master-disable，按回车键

3.输入你的账户密码，按回车键确认执行（该密码不会显示，直接输入即可）

![sudo](https://ae01.alicdn.com/kf/H609aefe4583e4063b7a3fe8638f759814.jpg)

### macOS Catalina 10.15以上

当电脑已经开启任何来源，但依旧打不开应用时：

1.打开终端（Terminal.app）

2.输入以下命令，按回车键

sudo xattr -d com.apple.quarantine /Applications/xxxx.app

> 注意：
* /Applications/xxxx.app 换成你的App路径,xxxx为软件名称.
* 针对软件名称有空格的App，则需要在软件名称之间加入 \ ，如软件Sublime Text，运行sudo xattr -d com.apple.quarantine /Applications/Sublime\ Text.app

3.输入你的账户密码，按回车键确认执行重启App即可

![macOS Catalina](https://ae01.alicdn.com/kf/H43467ef9ffca4cf19df9dffe8d091d21s.jpg)

**ChangLog**

2019.10.31

- 博客初拟
