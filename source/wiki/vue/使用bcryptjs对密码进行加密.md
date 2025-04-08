---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: 使用bcryptjs对密码进行加密
---

**用户注册或登录时，将密码进行加密。**

**DM Preview版本使用bcryptjs对密码进行加密**

1、安装

npm install bcryptjs

  

2、前端使用

import bcrypt from 'bcryptjs'

var salt = ' ' //自定义盐
var hashpwd = bcrypt.hashSync(pwd, salt)

  

**Prwiew2使用sha512**

1、安装

npm install js-sha512@latest

2、前端使用

import { sha512 } from 'js-sha512'

//preview2版本使用sha512加密
  var body = {
   email: username,
   password: sha512(pwd)
  }
    
  return (axios({
   method: 'post',
   data:body,
   url: url
  }));