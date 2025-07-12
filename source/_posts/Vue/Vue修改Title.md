---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue修改Title
date: 2024-7-08 11:00:00
category:
  - Vue
---

**main.js中修改**
```
//默认标题
document.title="VKSP\_Vue"

//路由动态修改
router.beforeEach((to,from,next)=>{
  if(to.meta.title){
    document.title=to.meta.title
  }
  next()
})
```
  

**route定义meta.title**
```
routes:\[
  {
    path:'/todo',
    component:Todo,
    meta:{
      title:"待办事项"
    }
  },
  {
    path:'/concept',
    component:Concept,
    meta: {
      title: "概念"
    }
  }
\]
```