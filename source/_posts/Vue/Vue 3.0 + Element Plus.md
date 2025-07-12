---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue 3.0 + Element Plus
date: 2024-7-08 11:00:00
category:
  - Vue
---

Vue发布了3.0版本，最好用的UI组件库Element UI也发布了适配的Vue 3.0的新版本Element Plus。  
这里记录使用Vue CLI来完成Vue 3.0项目搭建和使用Element UI。   

1、安装升级最新的Vue CLI 4.x # npm install -g @vue/cli 输入vue -V或者vue --version查看版本。 

2、创建Vue 3.0版本的项目 # vue create my-app 

3、项目引入Element Plus # vue add element plus 一路回车确认，Element Plus就自动添加到项目里啦！ Vue 3.0入口文件的变化： 相对于2.0版本的不同，3.0使用createApp（App）创建Vue的实例。然后使用熟悉的use来引入Element UI组件库。

 - 1）默认JS项目添加Element Plus： import ElementPlus from 'element-plus' import 'element-plus/lib/theme-chalk/index.css' createApp(App).use(ElementPlus)mount('#app') 
 - 2）添加TypeScript插件后项目添加Element Plus： import installElementPlus from './plugins/element' const app = createApp(App) installElementPlus(app) app.mount('#app')