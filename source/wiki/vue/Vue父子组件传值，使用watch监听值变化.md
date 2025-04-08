---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue父子组件传值，使用watch监听值变化
---

如果直接在子组件中的mounted中调用tododata,此时无法获取到传值数据，因为还未传过来。

使用watch进行实时监听：

  

**父组件：**

<TodoListCategory :todoData="tableData"/>

**子组件：**
```
props:{
    todoData:\[\]
 },
 watch:{
		todoData:{
   handler(newValue,oldValue){
    //console.log(newValue)
    //console.log(oldValue)
   }
  },
  deep:true,
 }
```