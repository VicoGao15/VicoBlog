---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue 2.0 + Eliment UI
category:
  - Vue
---

1、安装 #npm i element-ui -S  
2、引用 import ElementUI from 'element-ui'; Vue.use(ElementUI)   
3、如果是使用Vue-cli开发，记得安装babel-plugin-component，安装步骤：   
- 1）下载babel-plugin-component   
- 2）配置package.json文件 ts： "extends": \[ "plugin:vue/essential", "plugin:element-ui", "eslint:recommended", "@vue/typescript" \],