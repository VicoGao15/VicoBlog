---
menu_id: tutorial
title: 博客搭建-目标管理
date: 2024-08-15 13:12:22 
categories: 
  - 教程
leftbar: ['welcome','ghuser','tagcloud']
repo: vicogao15/vicoblog
---
{% hashtag 博客搭建 %}
{% hashtag 教程 %}

{% okr 目标 %}
2024年的小目标：完善 VicoBlog
来自2024-8-15年的复盘：已搭建好框架，接下来按照Stellar主题内容进行样式优化，以及后续文章内容的补充 {% emoji tieba 滑稽 %}

<!-- okr kr1 percent:1 -->
部署到Github Page
{% checkbox 在vicogao@126.com/VicoGao15的github账户下创建组织VicoBlog checked:true %}
{% checkbox VicoBlog组织下创建存放Hexo源码仓库VicoBlog-Hexo-SourceCode checked:true %}
{% checkbox VicoBlog组织下创建Githbu Page仓库vicoblog.github.io checked:true %}
{% checkbox 每个组织下都能创建Github Page，这以后就能搭建多个静态博客了，计划给樱同学搭建一个VikyBlog checked:true %}
{% checkbox symbol:minus color:yellow checked:true 图片资源加载速度太慢 %}
{% redio checked:true Github Page仓库同名域名访问: vicoblog.github.io %}
{% emoji blobcat blobcatthink%}

<!-- okr kr2 percent:1 -->
部署到vercel
{% checkbox vercel注册 checked:true %}
{% checkbox vercel关联Github账号 checked:true %}
{% checkbox 在vercel中导入Github的Hexo源码仓库创建项目，识别commit，自动构建部署 checked:true %}
{% radio checked:true 部署后vercel自动分配域名： {vercel project名称}.vercel.app %}
{% note color:red 国内被墙，需要翻墙访问!!! %}
{% emoji blobcat blobcatcomftears %}

<!-- okr kr3 percent:1 -->
部署到netlify 
{% checkbox netlify关联Github账号 checked:true %}
{% checkbox 在netlify中导入Github的Hexo源码仓库创建项目，识别commit，自动构建部署 checked:true %}
{% radio checked:true 部署后netlify自动生成Site name，访问域名：{Site name}.vercel.app %}
{% radio checked:true 可随时手动修改Site name，改变访问域名 %}
{% note color:blue 没有被墙，国内访问速度还不错 %}
{% emoji blobcat ablobcatattentionreverse %}最佳推荐!

<!-- okr kr4 percent:0.5 status:unfinished -->
Hexo配置完善
{% checkbox Hexo使用Stellar主题 checked:true %}
{% checkbox Hexo图片显示，hexo-renderer-marked插件 checked:true %}
{% checkbox hexo deploy 一键部署配置 checked:true %}
{% checkbox 左上角图标与网站icon checked:true %}
{% checkbox 修改文章默认url( _config.yml中设置 permalink: :title/ )，之后生成文章的 url 中就没有日期了 checked:true %}
{% checkbox 侧边栏背景图片 %}

<!-- okr kr5 percent:0.4 status:unfinished -->
Stellar主题中有很多好看的组件和相关配置，在VicoBlog中使用
{% checkbox 使用评论组件：Beaudar checked:true color:green %}
{% checkbox 使用timeline时间线组件 checked:true color:green %}
{% checkbox okr目标管理 color:green checked:true %}
{% checkbox swiper 轮播容器 color:green checked:true %}
{% checkbox 左侧小组件的使用(Github用户信息、标签云) color:green checked:true %}
{% checkbox 文章分类管理menu_id symbol:times color:red checked:true %}
{% checkbox 更改主题字体 symbol:times color:red checked:true %}
{% checkbox 添加顶部加载精度条 symbol:times color:red checked:true %}
{% link https://sfzhang.top/blog/2023/10/12/blog-progress Stellar主题添加顶部加载进度条 %}
{% checkbox 使用文档系统 symbol:times color:red checked:true %}
{% checkbox 实现「笔记」栏目 checked:true color:green %}
{% checkbox timeline获取github issue动态数据(REST API速率限制的问题) color:green %}

<!-- okr kr6 percent:0.2 status:unfinished -->
从有道云笔记中迁移部分笔记到博客
{% checkbox 各城市的游玩攻略、总结 %}
{% checkbox 日记 %}
{% checkbox 其他记录 %}

{% endokr %}

