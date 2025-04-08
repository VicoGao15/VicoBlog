---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue页面监听键盘按键上下左右
---

**1、监听方法**
```
// 监听键盘
  keyDown() {
   document.onkeydown = (e) => {
    //事件对象兼容
    let e1 = e || event || window.event || arguments.callee.caller.arguments\[0\]
    //键盘按键判断:左箭头-37;上箭头-38；右箭头-39;下箭头-40
    //左
    if (e1 && e1.keyCode == 37) {
     // 按下左箭头
     EventBus.$emit('LookBackOne',this.selectConcept.id)
    } else if (e1 && e1.keyCode == 39) {
     // 按下右箭头
     EventBus.$emit('LookNextOne',this.selectConcept.id)
    }
   }
  },
```
**2、在mounted 钩子函数中调用**

this.keyDown()

**3、组合建**
```
if (e1.ctrlKey && e1.keyCode == 37) {
     // 按下(ctrl+左)箭头
     EventBus.$emit('LookBackOne',this.selectConcept.id)
    } else if (e1.ctrlKey && e1.keyCode == 39) {
     // 按下(ctrl+右)箭头
     EventBus.$emit('LookNextOne',this.selectConcept.id)
    }
```
键盘keyCode：[https://www.toptal.com/developers/keycode/for/arrow-left](https://www.toptal.com/developers/keycode/for/arrow-left)