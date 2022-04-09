---
layout:     post
title:      "编程 | 离开和进入页面时改变title"
subtitle:   "有趣的代码万里挑一"
date:       2019-06-09 10:00:00
author:     "Lyle"
header-img: "img/post-bg-title.jpg"
header-mask: 0.5
catalog:     true
tags:
    - 编程
    - title
    - API
    - 有趣
    - 学习
---

# 离开和进入页面时改变title

最近浏览博客经常看到网页title神奇的一幕，可以在当浏览器中打开网页在离开页面后，title会变化些好玩的样式来吸引注意力，于是去查找对应的方式，来水一贴。

## 原理

使用了HTML5的Page Visibility API，有了API真的是一个很方便的事情啊！连代码都可以优雅的使用了。

页面可见性API有两个属性，一个事件，如下：

document.hidden: Boolean值，表示当前页面可见还是不可见

document.visibilityState: 返回当前页面的可见状态，取值有 hidden visible prerender preview

visibilitychange: 当可见状态改变时候触发的事件。

## 代码

```js
var OriginTitile = document.title;
var titleTime;
document.addEventListener('visibilitychange', function () {
    if (document.hidden) {
        document.title = '(つェ⊂)~偶哟，奔溃啦！ ' + OriginTitile;
        clearTimeout(titleTime);
        } else {
        document.title = '(*´∇｀*) 咦！又好了~ ' + OriginTitile;
        titleTime = setTimeout(function () {
            document.title = OriginTitile;
        }, 2000);
    }
});
```

## 实现效果

![](https://ae01.alicdn.com/kf/HTB1Vc3Fb21H3KVjSZFB762SMXXag.png)

**—— ChangeLog**

2019.06.09

- 博客初拟