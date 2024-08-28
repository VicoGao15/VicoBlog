---
layout: wiki  # 使用wiki布局模板
wiki: hexo_stellar # 这是项目名
menu_id: wiki
title: 樱同学-新手指南
date: 2024-08-07 13:40:22 
cover: /assets/cover/cover_ying.png
banner: /assets/cover/cover_ying.png
comments: true
---

### 部署流程
{% timeline %}
<!-- node 第一步 -->
打开软件`Visual Studio`，点击左上角菜单`File`->`Open Folder`，选择打开项目所在文件夹VickyBlog
> 在Visual Studio中第一次打开需要，后续打开visual Studio会自动打开上次的文件夹项目
<!-- node 第二步 -->
点击左上角菜单`Terminal`->`New Terminal`，打开一个命令行窗口在底部
<!-- node 第三步 -->
执行如下命令，更新云端代码同步到本地(不同步的话，提交更新会有冲突)
{% copy git pull prefix:> %}
<!-- node 第四步 -->
在项目的`source/_post`文件夹下创建一个md格式文件，如`日记.md`，在日记.md文件中编辑文章内容，ctrl+s保存
<!-- node 第五步(非必要) -->
执行如下命令，查看本地文件与云端文件的差别
{% copy git status prefix:> %}
会显示 add: 日记.md
<!-- node 第六步 -->
分别按顺序执行如下命令，将本地新建的文章文件上传到云端
{% copy git add * prefix:> %}
{% copy git commit -m "提交更新内容，可自定义填写" prefix:> %}
{% copy git push prefix:> %}  

> 注意自定义内容有引号：`git commit -m '提交更新内容，可自定义填写'`

{% endtimeline %}

{% note color:blue 以下内容旨在列举搭建个人站点的一些概念点，时刻翻阅了解其是什么，工作原理是什么。 %}
### Hexo 是什么？
[文档原文：](https://hexo.io/zh-cn/docs/)  
> Hexo 是一个快速、简洁且高效的博客框架。 Hexo 使用 Markdown（或其他标记语言）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

通俗理解：  
Hexo是一个框架，编辑Markdown语言编写文章，通过他的内部命令可以直接生成静态网站代码，静态网站代码可以部署到网络站点（如免费的Github Page），可远程网络访问。
### Markdown 是什么？
Markdown 是一种轻量级的标记语言，可用于在纯文本文档中添加格式化元素。文本内容存储在带有 .md 或 .markdown 扩展名的纯文本文件中
### Markdown 语法
**基本语法**：  
![基本语法](/assets/Postimg/VikyTutorial/markdown_base.png)

**扩展语法**：  
![扩展语法](/assets/Postimg/VikyTutorial/markdown_extend.png)
### Github Page是什么？
GitHub Pages 是 GitHub 提供给用户用来展示个人或者项目主页的静态网页系统。也就是说我们可以把项目代码写好后上传 GitHub，然后利用 GitHub Pages 为这个项目生成一个静态页面，别人通过网址可以访问我们的页面。Github Pages 只能托管静态站点。
### Github 是什么？
GitHub 是全球知名的代码开源平台。可以上传自己的代码到平台进行托管。
### Visual Studio Code 是什么？
一款非常好用的文本编辑器。

