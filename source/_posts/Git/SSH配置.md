---
layout: wiki  # 使用wiki布局模板
wiki: git # 这是项目名
title: ssh配置
category:
  - Git
---

##### 1.安装git
##### 2.GitHub上使用邮箱注册账号
##### 3.绑定用户名和邮箱
- 配置用户名（"username"是自己的账户名）
`git config --global user.name username`
- 配置邮箱（"email"注册账号时用的邮箱）
`git config --global user.email email`
#### 4.查看配置是否OK
`git config --global --list`
 
##### 5.生成ssh
`ssh-keygen -t rsa`
然后连敲三次回车键（也可以输入设置密码），结束后去系统盘目录下（一般在 C:\Users\你的用户名\.ssh）(mac: /Users/用户/.ssh）查看是否有.ssh文件夹生成，此文件夹中以下两个文件
{% image /assets/PostImg/Wiki-Git/ssh_generate.png %}

##### 6.添加公钥到Github
将ssh文件夹中的公钥（ id_rsa.pub）添加到Git服务器中（下面步骤是在GitHub管理平台上操作），在GitHub中点击右上角头像->Settings->SSH and GPG keys->New SSH key,将公钥（ id_rsa.pub）文件中内容复制粘贴到key中，然后点击Add SSH key就好啦！

##### 7.测试一下配置是否成功
```
ssh -T git@github.com
```

确认用户名正确即可。
{% image /assets/PostImg/Wiki-Git/ssh_config_test.png %}
