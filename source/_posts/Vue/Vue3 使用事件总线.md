---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue3使用事件总线
date: 2024-7-08 11:00:00
category:
  - Vue
---

Vue3中区别于Vue2无法直接使用$emit和$on，安装插件来使用事件总线：

1、安装mitt库

```npm i mitt ```

2、使用mitt库

可以在单独的文件暴露出事件总线对象

// mitt库默认导出的是一个函数，我们需要执行它从而得到事件总线的对象

/\* eventbus.js \*/ // 这里我们在js中暴露这个事件总线对象
```
import mitt from "mitt"; 
const emitter = mitt(); 
export default emitter; 
```
3、在指定组件中导入并使用它！

 // 这里我们导入我们单独写的暴露事件总线对象的js
```
/\* About.vue \*/ //

模板代码 <button @click="sendHomeContent">send</button>

// 导入事件总线

import emitter from "./utils/eventbus.js"; 

// methods代码

sendHomeContent(){
  // 触发自定义总线why，并传入一个对象 
  emitter.emit("why",{name:'why',age:19}) } 

/\* HomeContent.vue \*/

  // 导入事件总线 
  import emitter from "./utils/eventbus.js"; 
  // 在创建vue实例时，注册why事件总线 
  created(){ emitter.on("why",msg=>{ 
    console.log("HomeContent接收到得About发送得数据了：",msg); 
  }); 
  }
  ```