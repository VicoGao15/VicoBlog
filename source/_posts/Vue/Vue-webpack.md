---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue Webpack
date: 2024-7-08 11:00:00
category:
  - Vue
---

介绍Webpack基础的一篇好文章： https://juejin.cn/post/6921161482663100423  
官网： https://webpack.docschina.org/concepts/  
webpack是一个用于现代JacaScript应用程序的 ‘静态模块打包工具’。  

webpack四个核心概念：  
 - 入口（entry）：指示webpack应该使用哪个模块来作为构建其内部依赖图的开始  
 - 输出（output）：在哪里输出它所创建的bundles  
 - loader：让webpack能够去处理那些非JavaScript文件，比如vue-loader、style-loader、css-loader  
 - 插件（plugins）：用于执行范围更广的任务 webpack 与 Vue-cli的关系？ vue-cli里面包含了webpack，并且配置好了基本的webpack打包规则。