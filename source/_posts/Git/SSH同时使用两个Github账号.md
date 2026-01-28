---
layout: wiki  # 使用wiki布局模板
wiki: git # 这是项目名
title: SSH同时使用两个Github账号
date: 2025-1-01 11:00:00
category:
  - Git
---


### 一个工作环境中配置两个Github账号

需求：有多个Github账号时，想在一个电脑上同时使用，互不干扰。

在`C:\Users\{用户名}\.ssh`目录下打开gitbash，生成不同的SSH key

```
ssh-keygen -t rsa -C 'one@github.com'
ssh-keygen -t rsa -C 'two@github.com'
```

运行命令后不要一路回车，第一次对话出现“Enter file in witch to save key”的时候输入文件名，区分两次生成的ssh key。分别在两个github账号的setting处添加配置ssh key。

file: id_rsa
file: id_rsa.pub
file: id_rsa_two
file: id_rsa_two.pub

is_rsa和id_rsa.pub时默认的连接选择，当需要选择哪个账号连接时，将哪个的密钥文件重命名为is_rsa和id_rsa.pub即可，日后记得重新配置global user.name和user.email。

```
git config --global user.name 'username'
git config --global user.email 'email'
```

测试连接：
```
ssh -T git@github.com
```

确认用户名正确即可。