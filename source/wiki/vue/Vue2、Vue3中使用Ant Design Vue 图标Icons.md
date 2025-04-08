---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue2、Vue3中使用Ant Design Vue 图标Icons
---

```
import { UploadOutlined } from '@ant-design/icons-vue'
components(){
  UploadOutlined
}
```
template:
```
//Vue2
<a-icon type="upload"><a-icon>


//Vue3
<upload-outlined></upload-outlined>
```