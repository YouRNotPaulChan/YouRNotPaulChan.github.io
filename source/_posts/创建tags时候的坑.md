---

layout: post
title: 创建tags时候的坑
date: 2017-12-04 10:36:49
author: "陈越"
header-img: /postbackground.jpg
tags: 随手记

---

## start
  最近玩hexo有点不亦乐乎，一直踩坑一直爬坑，最近又发现了一个可能分分钟踩坑的地方
  在新建博文时，我们可能会使用tag，但在新建tag时我们一般用到的指令是

  ```bash
     hexo new page "tags"
  ```
  这样会在source文件夹中生成一个tags文件夹，其中会有一个index.md的文件，在里面
  的title增加如下的配置
  ```
     title: tags
     date: 当前日期
     layout: tags
  ```
  注意这里的冒号: 后面要有空格

  我在新建这个tags的时候踩了一个坑，没想到github page居然区分大小写，我新建的时候
  用成了
  ```bash
     hexo new page "Tags"
  ```
  也因此，我的tags才点开会进入404错误页面，如果踩中这种坑也不怕，其实还是很简单就能
  修复的，只需要将在source下已经新建出来的Tags文件夹删除了，然后重新执行

  ```bash
     hexo new page "tags"
  ```

  再重新执行上面的配置即可


## end