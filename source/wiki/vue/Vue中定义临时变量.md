---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue中定义临时变量
---

多层循环中定义临时变量保存一个复杂表达式 需要给隐藏，否则会显示出来
```
<p v-show="false">{{otherDetail=retContainerOtherDetailByName(item.name)}} </p>
<p>{{otherDetail.name}}</p>
```