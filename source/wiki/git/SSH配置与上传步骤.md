---
layout: wiki  # 使用wiki布局模板
wiki: wiki-git # 这是项目名
title: ssh配置与上传步骤
---

#### 1.git安装好后去GitHub上使用邮箱注册一个账号
#### 2.绑定用户名和邮箱
- 配置用户名 
`git config --global user.name "username" #（ "username"是自己的账户名） `
- 配置邮箱 
`git config --global user.email "emial" 	//("email"注册账号时用的邮箱)`
#### 3.查看配置是否OK
`# git config --global --list`
 
#### 4.生成ssh
`# ssh-keygen -t rsa`
然后连敲三次回车键（也可以输入设置密码），结束后去系统盘目录下（一般在 C:\Users\你的用户名\.ssh）(mac: /Users/用户/.ssh）查看是否有.ssh文件夹生成，此文件夹中以下两个文件
{% image /assets/PostImg/Wiki-Git/ssh_generate.png %}

#### 5.将ssh文件夹中的公钥（ id_rsa.pub）添加到Git服务器中（下面步骤是在GitHub管理平台上操作），在GitHub中点击右上角头像->Settings->SSH and GPG keys->New SSH key,将公钥（ id_rsa.pub）文件中内容复制粘贴到key中，然后点击Add SSH key就好啦！

#### 6.测试一下配置是否成功
{% image /assets/PostImg/Wiki-Git/ssh_config_test.png %}
显示如上就说明配置好啦！
