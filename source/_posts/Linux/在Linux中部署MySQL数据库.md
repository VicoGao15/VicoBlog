---
title: 在Linux中部署MySQL测试数据库
date: 2025-7-10 14:00:00
category:
  - Linux
banner: /assets/cover/doc.jpg
---

1、查看是否已经安装了MySQL  
- rpm是Linux发行版常用的软件包管理器
- rpm -qa: 显式所有已安装的软件包  
`rpm -qa | grep mysql`

2、下载MySQL安装包  
- wget是Linux用于从Web下载文件的命令行工具，支持http、https、ftp  
`wget -i -c http://dev.mysql.com/get/mysql57-community-release-el7-10.noarch.rpm`

3、安装MySQL包  
- yum是基于rpm包管理，能够从指定服务器下载rpm包并且安装
- yum -y: 参数-y表示安装过程中所有操作都选择“Yes”  
`yum -y install mysql57-community-release-el7-10.noarch.rpm`

4、安装MySQL  
`yum -y install mysql-community-server`

5、启动MySQL服务  
`systemctl start mysqld.service`

6、查看MySQL运行状态  
`service mysqld status`
`ps -ef|grep mysql`

7、连接MySQL  
`mysql -u root -p`

8、重置密码
- MySQL安装后有初始密码，查看初始密码：  
`grep 'password' /var/log/mysqld.log`

- 连接MySQL：  
`mysql -u root -p`

输入初始密码，会出现错误，因为MYSQL5.7之后需要先修改初始化密码。  
- 修改MySQL配置文件my.cnf：  
`vim /etc/my.cnf`

进入my.cnf,在配置文件中添加skip－granp－tables

- 按ESC，输入:wq保存并退出，然后关闭mysql服务：  
`service mysql stop`

- 重启mysql服务： 
`service mysql start`

- 然后再次连接mysql：  
`mysql -u root -p`

- 输入任意密码即可查看数据库：  
`show database;`

- 重置密码：
`update user set authentication_string=password('密码') where user='root';`

设置完成后，删除my.cnf文件中添加的skip-grant-tables，重启MySQL服务，重新登录即可


https://blog.csdn.net/weixin_60692635/article/details/130673486