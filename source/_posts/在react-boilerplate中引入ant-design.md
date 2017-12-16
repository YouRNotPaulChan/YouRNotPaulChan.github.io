---
title: 在react-boilerplate中引入ant-design
date: 2017-12-16 16:43:41
author: "陈越"
header-img: /AberystwythSeafront.jpg
tags: 随手记
---

## start

> 最近发现一个阿里的基于react开发的组件库 [ant-design](https://ant.design/index-cn)，提供了一些可以在
react项目中快速使用的组件，例如说一个按钮，一个input框，一个日期选择框等等，如果想在自己已有的项目中引用的话
就需要有一些配置，由于官方给的教程是在create-react-app这个脚手架中引入的，但是我使用的脚手架是 [react-boilerplate](https://github.com/react-boilerplate/react-boilerplate),所以在配置的时候遇到了一些问题，也踩了不少坑，终于引入成功了，特此放上来share一下  
  
> 如果是想在项目刚开始的时候引入的话，那没问题，直接克隆已经引入ant-design的react-boilerplate就行了
  ```bash
  git clone https://github.com/react-boilerplate/react-boilerplate.git
  ```
> 但是如果是已有的项目怎么办呢？那就需要一些安装和配置了，首先在项目根目录使用npm安装antd组件包
  ```bash
  npm i antd -S
  ```
> 接着在项目的package.json文件中可以看到引入了antd及版本号
  ![](http://p061xvmi7.bkt.clouddn.com/package_json.png)

> 到这一步，就可以在项目中引入antd的组件了，在/app/app.js 文件中引入antd
  ```
  import 'antd/dist/antd.css'
  ```

> 然后在想使用的地方使用如下语句引入组件，下例演示如何引入一个按钮组件
> ![](http://p061xvmi7.bkt.clouddn.com/how2button.png)
  效果
  ![](http://p061xvmi7.bkt.clouddn.com/buttonimg.png)
> 如果按照以上方法引入的话，在开发环境打开console，你会发现如下的提示
> ![](https://zos.alipayobjects.com/rmsportal/GHIRszVcmjccgZRakJDQ.png)
  这是提示你要使用按需使用antd组件，而不是全部加载，因为这个可能会导致前端的性能问题，
  因此，按照它的提示，我们需要使用一下写法来引入组件
  ```bash
  import Button from 'antd/lib/button';
  import 'antd/lib/button/style'; // 或者 antd/lib/button/style/css 加载 css 文件
  ```


> 但是，如果这样的话每次引入组件都会很麻烦，如果你有使用babel的话，就可以使用[babel-plugin-import](https://github.com/ant-design/babel-plugin-import)
  插件来按需加载，加入了这个组件之后，你依然可以使用以下写法引入组件
  ```bash
  import {Button} from 'antd';
  ```

> 在项目根目录下安装babel-plugin-import
  ```bash
  npm i babel-plugin-import -D
  ```
> 接着在项目的/internals/webpack/webpack.base.babel.js中添加如下配置
  ![](http://p061xvmi7.bkt.clouddn.com/webpackbabelconfig.png)

> 然后运行以下命令，重新加载一遍dll
  ```bash
  npm run build:dll
  ```
> 现在可以直接在项目中引入组件，而且开发环境的console中也不会出现上面的提示，就说明成功了

> 以上

## end