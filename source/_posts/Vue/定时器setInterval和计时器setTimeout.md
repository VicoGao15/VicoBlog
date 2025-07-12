---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: 前端定时器 setInterval 和 setTimeout setInterval
date: 2024-7-08 11:00:00
category:
  - Vue
---

前端定时器 setInterval 和 setTimeout setInterval

循环执行 循环执行就是设置一个时间间隔，每过一段时间都会执行一次这个方法,直到这个定时器被销毁掉。 用法是setInterval（“方法名或方法”，“延时”）， 第一个参数为方法名或者方法，注意为方法名的时候不要加括号，第二个参数为时间间隔（毫秒）。 设置循环执行

  

this.timer = setInterval(this.updataDevice, 5000)

  

// 第一个参数：this.updataDevice 是ts中的方法，只写方法名不写括号。

// 第二个参数：5000 表示延时，毫秒，5000毫秒=5秒，即执行完本次后，隔5秒再次执行

  

销毁定时器 案例是vue写的，用vue举例：

beforeDestroy() { // 组件销毁前执行
clearInterval(this.timer) // 清除定时器
this.timer = null // 定时器的变量赋值null
},

  

setTimeout 定时执行

定时执行setTimeout是设置一个时间，等待时间到达的时候只执行一次，但是执行完以后定时器还在，只是没有运行。 用法是 setTimeout(“方法名或方法”, “延时”); 第一个参数为方法名或者方法，注意为方法名的时候不要加括号，第二个参数为时间间隔。

设置定时执行

setTimeout(() => {
this.showMarker() // 执行的方法
}, 1000) // 时间 1000毫秒 = 1秒