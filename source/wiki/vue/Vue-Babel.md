---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue-Babel
---

官网： https://www.babeljs.cn/ Babel是什么？ 一个JavaScript编译器 

一句话，Babel能把你写的JS变成其他版本的JS。 

比如写ES6标准的JS： \[1,2,3\].map(n=>n+1); 

Babel可以把它翻译为ES5： \[1,2,3\].map(function(n){ return n+1; }); 

这样一来，就可以写IE不支持的ES6 JS语法了，因为被翻译成了IE支持的ES5 JS语法。