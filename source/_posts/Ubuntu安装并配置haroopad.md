---

layout: post
title: Ubuntu安装并配置haroopad
date: 2017-12-13
author: "陈越"
header-img: /rainbackground.jpg
tags: 随手记

---


## start
  >写Markdown的时候人们都喜欢能实时的预览效果，最近在编写hexo博客的时候,由于采用Markdown的语法，每次写完都需要去页面刷新一遍才能看到，有时候还需要重新生成一遍页面才可以看到效果，这样写博客的效率会变低，于是我就去找适合Ubuntu系统使用的Markdown的编辑器 
 
 　　![](http://p061xvmi7.bkt.clouddn.com/haroopad.png) [haroopad](http://pad.haroopress.com/user.html)是一款不错的全平台Markdown编辑器，由于已使用性和轻便性，在各个平台上都有很多使用者，以下就介绍如何在Ubuntu上安装和配置Haroopad。
   
   
  > #### 首先下载Haroopad的安装包，可以在[官网下载](https://bitbucket.org/rhiokim/haroopad-download/downloads/haroopad-v0.13.1-x64.tar.gz)
  >  然后将下载的压缩包放进``~/opt/haroopad``文件中
    
  >  ``` bash
     cd ~/opt/haroopad #进入haroopad文件中
     ```
    
  >  ``` bash
     tar zxvf haroopad-v0.13.1-x64.tar.gz -C haroopad.v0.13.1.x64
     #解压安装包，并放进haroopad.v0.13.1.x64文件夹中
     cd haroopad.v0.13.1.x64
     #进入haroopad.v0.13.1.x64文件夹中
     tar zxvf data.tar.gz
     #解压data.tar.gz　
     sudo cp -r ./usr /
     
     tar zxf control.tar.gz
     #解压control.tar.gz
     chmod 755 postinst
     #赋予运行权限
     sudo ./postinst
     #运行./postinst安装
     ```

  >  #### 修改桌面图标
  >    如下：Icon的配置

  >  ```bash
      sudo vi /usr/share/applications/Haroopad.desktop
     ```
  >  ```bash
      [Desktop Entry]
      Name=haroopad
      Version=0.13.1
      Exec=haroopad
      Comment=The Next Document processor based on Markdown
      #Icon=haroopad
      Icon=/usr/share/icons/hicolor/128x128/apps/haroopad.png #换图标
      Type=Application
      Terminal=false
      StartupNotify=true
      Encoding=UTF-8
      Categories=Development;GTK;GNOME;
     ```

## end