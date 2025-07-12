---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue3 Router
date: 2024-7-08 11:00:00
category:
  - Vue
---

Vue 3迁移。  
//定义路由  
import { createRouter, createWebHistory} from 'vue-router'  
//import { router } from './route' const router=createRouter({ history:createWebHistory(), routes:\[ {path:'/',component:App}, {path:'/concept',component:Mock}, {path:'/todo',component:HelloWorld}, \] })