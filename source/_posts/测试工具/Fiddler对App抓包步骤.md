---
title: Fiddler－APP抓包步骤
date: 2025-7-11 15:00:00
category:
  - 测试工具
tags: [面试]
banner: /assets/cover/doc.jpg
---

https://zhuanlan.zhihu.com/p/541265095

#### 前提条件
手机和启动了Fiddler的PC必须处于同一个局域网，同一个Wifi。

#### 一、配置PC端Fiddler
Tool -> Fiddler Options -> Connections
- 监听端口默认为 8888 即可
- 勾选 “Allow remote computes to connect”

#### 二、移动端配置Wifi代理
- 服务器主机：pc端ip,刚刚设置的8888端口
- 手机端wifi配置手动代理

#### 三、移动端安装证书
- 访问网址：主机＋端口，下载证书安装
- 可能访问不了，需要在Fiddler中开启https：勾选Tool -> Fiddler Options -> Https -> Decrypt HTTPS traffic
- 安装CA证书
- 在手机设置中安装CA证书：https://blog.csdn.net/weixin_43856764/article/details/120442011

#### 4、在Fiddler中过滤，只抓取移动端的数据包
Tool -> Fiddler Options -> Https -> "from remote clients only"

