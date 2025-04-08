---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: 使用Vue Cli报错
---

ERROR Failed to get response from https://registry.npmjs.org/vue-cli-version-marker   

解决方案：  
1、清除缓存 # npm cache clean --force   
2、打开C:\\Users\\appeon\\.vuerc文件，修改配置为 { "useTaobaoRegistry": false, "packageManager": "npm" } 其中npm代表当前所使用的包管理方式，如果使用yarn需要将其对应修改。