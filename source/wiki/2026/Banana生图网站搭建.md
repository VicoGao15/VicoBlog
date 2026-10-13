---
layout: wiki  # 使用wiki布局模板
wiki: twosix # 这是项目名
title: Banana生图网站搭建
banner: /assets/cover/note.jpg
password: 10080353
---

# 调研
### 第三方api平台
https://4sapi.com/console
https://new.12ai.org/console
https://zxunai.com  
https://poloapi.com

### 竞品平台
https://nano.580ai.net/
https://banana.147ai.com/  
https://tu0.top/


# 技术实现
### 代码仓库
https://github.com/VicoGaoDev/BananaWeb

### 腾讯云（微信主账户登陆）
价格计算-todo  
控制台：https://console.cloud.tencent.com/

CloudBase云开发：https://tcb.cloud.tencent.com/dev?envId=banana-ai-4g7iqw0p1cab24e3  
（前端静态网站部署 + 后端API + MySQL数据库）  
数据库账户：vicogao/@Vico202204
```
DB_CONFIG = {
    "host": "sh-cynosdbmysql-grp-kmfw4ojg.sql.tencentcdb.com",
    "user": "vicogao",
    "password": "@Vico202204",
    "database": "banana800ai",
    "port": 20396
}
```

### 腾讯COS存储桶
价格计算-todo  
https://console.cloud.tencent.com/cos/bucket

### 购买域名
bananaimage.cn  
banana800ai.com  
banana800ai.cn  
banana800ai.cloud

# 部署
腾讯云CloudBase 199元/月的标准会员。  
### 前端-静态网站托管


### 后端-云托管
需要升级到标准会员才能连接CloudBase内网SQL数据库（设置同一个VPC）
