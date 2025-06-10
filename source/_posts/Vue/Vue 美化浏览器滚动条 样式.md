---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue美化浏览器滚动条样式
category:
  - Vue
---

直接加到App.vue的style中：
```
::-webkit-scrollbar-track { 
	background: rgba(0, 0, 0, 0.1); 
	border-radius: 0; 
} 
::-webkit-scrollbar { 
	-webkit-appearance: none; 
	width: 6px; height: 6px; 
} 
::-webkit-scrollbar-thumb { 
	cursor: pointer; 
	border-radius: 5px; 
	background: rgba(0, 0, 0, 0.15); 
	transition: color 0.2s ease; 
}
```