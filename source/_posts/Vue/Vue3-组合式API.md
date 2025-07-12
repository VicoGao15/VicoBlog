---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue3-组合式API
date: 2024-7-08 11:00:00
category:
  - Vue
---

Vue3使用组合式API=>Setup Vue2=>created、data、methods、computed 组合式API： 1、定义响应式变量： 有两种形式： 1）ref ,定义基本数据类型 2）reactive, 定义引用类型 2、使用路由：Setup中无法访问this，所以不能直接访问this.$router或者this.$route了。相反，我们使用useRouter函数： import {useRouter,useRoute} from 'vue-router' const route=useRoute()//使用参数 const router=useRouter()//使用路由跳转push console.log(route.params.id) router.push(' ') https://next.router.vuejs.org/guide/advanced/composition-api.html