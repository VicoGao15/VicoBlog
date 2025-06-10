---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: vue后端接口写成配置文件(axios获取本地json数据)
category:
  - Vue
---

vue3： 将serverConfig.json放到public目录下，build的时候该文件不会被编译，而是完整地保留在dist根目录。 vue中js使用： 如果是product正式环境： if (process.env.NODE\_ENV == 'production') { getConfigHost().then(res=>{ //Doing }) } function getConfigHost(){ return axios.get('./serverConfig.json') }