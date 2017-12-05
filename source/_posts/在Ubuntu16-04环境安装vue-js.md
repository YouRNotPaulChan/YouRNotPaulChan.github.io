---

layout: post
title: 在Ubuntu16.04环境安装vue.js
date: 2017-12-04 18:07:49
author: "陈越"
header-img: /3background.jpg
tags: 随手记

---

## start
  最近打算尝试一下前端开发，刚好目前公司有前端项目启动，我抱着试一试的心态加入了
  团队，由于选择的是vue.js，所以我花了一下午在电脑安装了vue.js的环境，由于我的
  电脑使用的是Ubuntu16.04系统，所以下面所经历的过程都是在Ubuntu系统操作的

  ### 1、首先需要安装node.js，并且是稳定版本，建议是6.10.3
  （原来我是4.2.6的所以老是导致后面的webpack安装报错）

  从官网上面下载nodejs6.10.3版本 
  英文网址：[https://nodejs.org/en/download/](https://nodejs.org/en/download/)
  中文网址：[http://nodejs.cn/download/](http://nodejs.cn/download/)
  下载tar.gz到本地目录下，然后解压，可以将名字改为nodejs,这样比较方便记住地址:

  ``` bash
  tar -xvf   node-v6.10.0-linux-x64.tar.xz
  mv node-v6.10.0-linux-x64  nodejs
  ```

  接着建立软链接，变为全局:
  ``` 
  ln -s /app/software/nodejs/bin/npm /usr/local/bin/ 
  ln -s /app/software/nodejs/bin/node /usr/local/bin/
  ```
  其中，app/software是你安装nodejs的目录，根据自己的地址需要修改，
  最后，检查一下nodejs是否安装成功:
  ``` bash
  node -v
  ```

  ### 2、安装webpack2.5.1版本
  webpack相当于模块加载器兼打包工具

  ```bash
  npm install -g webpack //全局安装
  npm install -g webpack-dev-server //安装调试工具
  ```

  webpack和webpack-dev-serve都需要全局安装，之前由于nodejs安装版本不对，每次安装之后
  都会报错，安装成功之后，执行以下命令:
  ```bash
  webpack -v //查看webpack版本
  webpack-dev-server -v //查看webpack-dev-server版本
  ```

  ### 3、安装vue-cli
  按照以下命令:
  ```bash
  npm install -g vue-cli //全局安装vue-cli
  vue init webpack projectname // 这里会让你重新输入一遍项目名，只能小写，之后生成项目名为ProjectName的模板
  cd ProjectName //进入项目文件
  npm install //初始化安装
  ```

  以上的命令在我的系统中经常会出现因为权限限制不能创建的问题，如果出现这种问题
  的话，只需要在命令前加入sudo就行了

  最后，执行:
  ```
  npm run dev
  ```
  在浏览器中打开localhost:8080就可以看到如下画面了
  ![](http://p061xvmi7.bkt.clouddn.com/vuejs.png)

  如果已经安装了nodejs想升级版本的话，可以执行如下命令
  ```bash
  npm cache clean -f //清除npm cache
  npm install -g n //安装node的n模块
  n stable //升级至最新稳定版本
  ```
  如果需要安装指定版本的话，可使用
  ```bash
  n 6.10.3  //这里的 6.10.3 是需要指定的版本号
  ```
  升级npm版本的话
  ```bash
  npm -g install npm
  ```

  ### 4、遇到的错误
  在第三步创建新的项目之后，在项目文件夹中执行npm install报错，报错信息如下
  ![](http://p061xvmi7.bkt.clouddn.com/vuejserrorphoto.jpg)
  这是因为chromedriver这个下载不了导致的，搜索了vuejs的github主页里的[issues](https://github.com/vuejs/vue-router/issues/261#issuecomment-218618180)，发现
  有个解决方法，就是将chromedriver的cdn改成国内淘宝的cdn
  执行如下命令:
  ```bash
  npm install chromedriver --chromedriver_cdnurl=http://cdn.npm.taobao.org/dist/chromedriver
  ```
  谢谢观看

## end