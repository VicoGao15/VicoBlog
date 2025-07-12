---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue中函数有回调参数，添加参数时如何调取默认回调参数
date: 2024-7-08 11:00:00
category:
  - Vue
---

**回调参数直接使用：**
```
<a-menu @click="menuItemClick"></a-menu>

menuItemClick(obj){
  console.log(obj)
}
```
**想传递参数进去：**
```
<a-menu @click="menuItemClick(a,b)"></a-menu>

menuItemClick(a,b,obj){
  console.log(obj)//打印undefined
}
```
**正确方式：**
```
<a-menu @click="menuItemClick(a,b,$event)"></a-menu>

menuItemClick(a,b,obj){
  console.log(obj)//打印正常回调参数
}
```
**原因分析：**

不写实参的方法menuItemClick默认传event，menuItemClick()和menuItemClick(a,b)等方式都写了实参，event就不见了。

所以补充事件以外的参数需要自己写上**$evnet**