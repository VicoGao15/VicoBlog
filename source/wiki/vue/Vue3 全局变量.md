---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue3全局变量
---

1.main.js中定义全局变量apiUrl ： con.config.globalProperties.$apiUrl ="http://172.16.100.62/api.vksp/api" 2.组件中使用全局变量apiUrl ： import { getCurrentInstance } from 'vue' const globalApi=getCurrentInstance()?.appContext.config.globalProperties.$apiUrl