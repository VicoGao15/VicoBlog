---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue路由中的#去掉
date: 2024-7-08 11:00:00
category:
  - Vue
---

vue路由中的#号 去掉 在使用vue进行开发的时候我们会发现地址栏上的ip后面会跟着一个#号，如果想去掉这个井号，我们可以在路由上加上 mode: 'history', 即可去掉
```
export default new Router({ 
  mode: 'history', 
  routes: \[ { 
    path: '/', 
    name: 'Home', 
    component: Home 
  }\] 
}) 
```

vue-router默认是hash模式，在hash模式下，是会有#号在URL上。

切换到HTML5的history模式，只需要在mode选项中配置即可。

在history模式下，URL就像正常的URL一样，但是该模式下需要后台正确的配置才可以。

因为在路由中传参时，后台没有配置好的话，就会返回404