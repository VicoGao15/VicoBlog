---
title: Fiddler
date: 2025-7-08 11:00:00
category:
  - 测试工具
tags: [面试]
banner: /assets/cover/doc.jpg
---
### 
### 一、工作中用到Fiddler的场景

- 主要是对客户端的应用进行抓包，查看接口数据
- 比如使用Fiddler对APP进行抓包
- 对IDE进行的用户反馈模块进行抓包测试
- 安装测试的弱网模拟（弱网测试）

`对于浏览器网页应用是不需要用到Fiddler抓包的，因为浏览器自带F12打开开发者工具调试,在网络模块即可查看到各接口数据包的详细情况`  
`开发者工具四个常用的功能模块：元素（ELements）、控制台（Console）、源代码（Sources），网络（Network）  `

### 二、Fiddler的工作原理
- 客户端与服务端的中间代理，能够监听他们之间的HTTP通信，截取请求和响应数据

### 三、数据包具体查看哪些参数
- Fiddler的监控面板分为两部分，左边显式抓取到的HTTP会话基本信息，包含：HTTP状态码、URL、响应时间、主机服务器IP等
- 右边分为上下两部分：
  - 上部分为请求的相关信息，查看：请求url、参数、请求实体等
  - 下部分为响应的相关信息，关注：响应的服务器、响应状态码、响应数据、响应时间等

### 四、Fiddler进行弱网测试
- 启动弱网
  - Fiddler－>Rulde->Performance->勾选Simulate Modem Speeds
  - 启动之后网络就慢下来了，因为在系统里面已经设置好了网络参数值
- 修改网络参数值
  - Rules->Customize Rules, 打开Fiddler ScriptEditor
  - 找到如下代码段，`M_Simulate = true`表示开启了弱网；300、150分别是系统设置的request和response的时间阈值，可手动修改
  ```
  if(M_SimulateModem){
  
    oSession["request-trickle-delay"] = "300";
    
    oSession["response-trickle-delay"] = "150";
  }
  ```
- 浏览器开发者工具有自带的模拟弱网功能：Network功能栏，可选择在线、2G、3G、离线