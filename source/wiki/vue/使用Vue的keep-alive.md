---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: 使用Vue的Keep-alive
---

#### 一.场景需求

常见的场景：

*   主页—>列表页—>详情页，
*   详情页—>列表页，
*   详情页—>主页—>列表页

我们希望，

从 **详情页—>列表页** 的时候页面的状态是缓存，不用重复请求数据，提示用户体验

从 **列表页—>主页** 的时候注销掉列表页缓存，以便在重新进入列表页的时候，获取最新数据

#### 二.实现

##### 1.详情页—>列表页**，**路由使用缓存

1）路由上添加keepalive为true，该页面缓存，进去不会刷新
```
{
  path: '/concept',
  name: 'concept',
  layout: "dashboard",
  component: () => import('../views/Concept.vue'),
  meta:{noCache:false, keepAlive:true}
 },
```
2）在app.vue中添加
```
<keep-alive>
  <router-view v-if="$route.meta.keepAlive"></router-view>
</keep-alive>
<router-view v-if="!$route.meta.keepAlive"/>
```
3）返回到缓存页面

this.$router.back()

##### 2.列表页—>主页**，**注销缓存

TODO