---
layout: post
title: react-native指定启动终端
date: 2018-03-19 17:10:34
tags: 随手记
author: "陈越"
header-img: /18-3-19/62605049.jpg
---

### start
  最近开始学习react-native开发iOS的app，安装过程不是太难，网上随便一找就是
一堆的教程，但是我是使用macos环境，iterm2终端，在每次执行
```
  react-native run-ios
```
以后，会在iterm2跑![](http://p061xvmi7.bkt.clouddn.com//18-3-19/44532978.jpg)
这样的一个窗口，跑完之后会打开自带的bash打开模拟器的启动器，这样一下子就出现
了两个终端，不管是运行或者是美观性管理性都不是太强，作为一个有强迫症的码农，
怎么可以忍受这种情况呢，所以这篇博客我就来研究一下如何在同一个终端运行ios模
拟器启动器。

  首先，我查看了一下stackoverflow上的解答,解答都是在项目 /node_modules/react-native/scripts/launchPackager.command 文件改一下打开方式，但是我一直找不到
这个文件夹，直到我重新运行了一遍上面那行启动命令，在第二个打开的bash中发现了
一句
```
  ~/react/DemoApp/node_modules/react-native/packager ~
```
如果按照路径去启动的话，那么会不会就在这个路径里呢？直接在finder里打开这个路径
果然发现这个文件
![](http://p061xvmi7.bkt.clouddn.com//18-3-19/95331199.jpg)
然后右键单击该文件，弹出的下拉菜单的时候按住option键,打开方式就会变成始终以
该方式打开，点击选择你需要用来打开的软件了，如果该方法不奏效，可以点击选中这
个文件，按 command+I 调出显示简介窗口
![](http://p061xvmi7.bkt.clouddn.com//18-3-20/52230169.jpg)
在画红框位置选择以什么方式打开，如果需要可以在下面选择全部更改，以后就会用你选
中的软件打开此类文件了。

以上
### end
