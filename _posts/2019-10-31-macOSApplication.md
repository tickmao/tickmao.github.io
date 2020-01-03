---
layout:     post
title:      "Mac应用程序无法打开或文件损坏的处理方法"
subtitle:   "第三方源App安装问题解决方案"
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

Mac用户在升级到最新系统macOS Catalina后，当安装 Mac 应用时，经常会遇到如下提示：
* “ XXX.app 已损坏，打不开。您应该将它移到废纸篓 ”
* “ 打不开 XXX.app，因为它来自身份不明的开发者 ”

当遇到这种情况后，需要对系统权限进行调整才可使用App。

### 一、开启任何来源

当安装第三方源App时：

1.打开终端（Terminal.app）

2.输入以下命令，按回车键

sudo spctl --master-disable

3.输入你的账户密码，按回车键确认执行（该密码不会显示，直接输入即可）

![sudo](https://ae01.alicdn.com/kf/H609aefe4583e4063b7a3fe8638f759814.jpg)

一般情况，开启任何来源后即可打开App，但 mac 最新系统需要另外做设置。

### 二、macOS Catalina 10.15以上

当电脑已经开启任何来源，但依旧打不开应用时：

1.打开终端（Terminal.app）

2.输入以下命令，按回车键

sudo xattr -d com.apple.quarantine /Applications/xxxx.app

> 注意
* /Applications/xxxx.app 换成你的App路径，xxxx为软件英文名称。
* 针对软件名称有空格的App，则需要在软件名称之间加入 \ ，如软件Sublime Text，运行sudo xattr -d com.apple.quarantine /Applications/Sublime\ Text.app

3.输入你的账户密码，按回车键确认执行重启App即可

![macOS Catalina](https://ae01.alicdn.com/kf/H506eaa5434ab4fe7ad4faa167529477b2.jpg)

**ChangLog**

2019.10.31

- 博客初拟
