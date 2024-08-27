---
layout: wiki  # 使用wiki布局模板
wiki: hexo_stellar # 这是项目名
menu_id: wiki
title: Hexo环境准备和快速建站
date: 2024-08-06 20:04:22
tags: 
  - Hexo
  - Github Page
  - Nodejs
categories: 
  - 教程
---

本文档介绍如何从零开始利用Hexo生成静态网站，并部署到Github Page中运行。 

文档内容包括：  
- 本地环境准备  
- 创建Hexo项目  
- 部署到Github Page  
- 使用Gittalk评论


## 本地环境准备
| Item      | Description | 链接 |
| ----------- | ----------- | ----------- |
| Git      | Git是版本库管理工具，用于将Hexo代码托管到Github进行管理。       | [下载安装](https://git-scm.com/download/win)       |
| NodeJs   | Nodejs是本地运行Hexo的运行库。注意Hexo兼容的Nodejs最高版本。        | [下载地址](https://nodejs.org/zh-cn/download/prebuilt-installer)       |
| Github账号 | 先在Github中注册一个账号，用于托管代码。 | [Github](https://github.com) |

## 创建Hexo项目
1. 安装完Nodejs后，安装Hexo-cli：  
``` bash
$ npm i -g hexo-cli
```
2. 安装Hexo：  
``` bash
$ npm i hexo
```
3. Hexo安装完成后，使用init初始化创建本地Hexo项目
``` bash
$ hexo init <项目名称>
```
4. 使用主题：  
- [1] 下载主题
- [2] 将下载的主题文件夹拷贝到hexo项目themes目录下
- [3] 在_config.yml配置文件中将theme修改为主题目录


## 部署到Github Page
### Github Page创建
在Github账号中创建一个仓库，名称为:  *[github账号用户名].github.io*
### Hexo部署
在Hexo项目目录下，打开cmd，执行build。
``` bash
$ hexo generate
或 
$ hexo g
```
在项目目录下就会生成publish文件夹，publish文件夹的内容就是静态网站，将这些内容上传到Github仓库 *[github账号用户名].github.io*， 就可以访问了。


{% link https://vicoblog.netlify.app %}




