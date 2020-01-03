---
layout:     post
title:      "MAC 外接显示器屏幕开启 HiDPI"
subtitle:   "脚本运行，简单粗暴"
date:       2019-11-14 22:00:00
author:     "Tickmao"
header-style: "text"
catalog:     true
tags:
    - macOS Catalina
    - Mac
    - 外接显示器
    - HiDPI
    - 脚本

---

趁着双十一终于下定决心跟着节奏更换了自己的显示器。在未换显示器之前用的依旧是我的 1080 的 dell 显示器。这次更换的为 dell 2719DS 。以下内容主要针对使用 2k 显示器的用户。非目标用户可以直接关闭当前页面。

在开始之前，讲两个Tips：

* 如果有条件，MAC 外接屏幕优先选择 4K 屏，可以支持自动开启 HiDPI。低于 4K 的屏幕则需要非官方途径开启；

* 在外接屏幕强制开启 HiDPI，即使是 2K 屏，也没有原生 Retina 屏幕细腻。

## 一、临时关闭系统保护（SIP）

重启你的Mac电脑，在开机声响起后按住 command+R 进入 recovery mode。在更多工具中，找到终端 Terminal，在终端输入关闭 SIP 的命令行语句，回车结束：

```zsh
csrutil disable
```

SIP 关闭成功后。重启电脑。

## 二、运行脚本

在终端输入以下命令回车即可：

```Zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi-zh.sh)"
```

![脚本运行图](https://github.com/xzhih/one-key-hidpi/raw/master/img/run-zh.jpg)

如果是外接屏幕，需要将笔记本盒盖后，再运行脚本，未盒盖则选择对应的显示器型号即可。

按照脚本的提示输入即可。2K 屏或 1080P 屏幕请按照外界屏幕的分辨率选择。

> 我的分别是1、3、2。

设置成功后，需要重启生效。

> 系统设置 - 显示器设置，外接屏幕已经开启了 HiDPI, 如下图所示，可以选择 “较大文字” 或 “更多空间”。

![](https://github.com/xzhih/one-key-hidpi/raw/master/img/preferences.jpg)

* 特别说明：

按住Optinon同时点缩放即可出现更多分辨率选项，我使用的分辨率是 1920 x 1080。

> 脚本源地址
[Github](https://github.com/xzhih/one-key-hidpi/blob/master/README-zh.md)

## 三、重新开启 SIP

为保证系统安全，在设置成功后，按照步骤一再次进入恢复模式，并在终端输入以下命令：

```zsh
csrutil enable
```

SIP 已重新开启。

## 关于外接显示器特别说明

1.一块 27 寸 / 32 寸的屏幕会让你爱不释手，提高生产力。如果 2k 选择 27 寸较好， 4k 则选择 32 寸更好；

2.外接屏幕需要占用 CPU、内存和显卡。比较老的电脑，可能带不动 2K/4K 屏幕，尤其在播放视屏时 / 滚动网页时会掉帧、卡顿，所以选购之前请咨询清楚；

3.Windows 和 Mac 选购设置有所不同，比如我 Mac 使用该屏幕时选择开启 HiDPI 并选择 1920 x 1080，Windows 我选择为 125% 的缩放；

4.请关注刷新率的小伙伴，在 Mac 上实现 4K 60HZ 对线材和接口是有要求的。

5.4k 60Hz 或是 2k 144Hz 的用户，完全根据本人的使用情景，如果游戏玩的较多那就后者，否则可以选择前者。

**ChangLog**

2019.11.14

- 博客初拟
