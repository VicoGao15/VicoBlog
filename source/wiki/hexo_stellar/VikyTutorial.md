---
layout: wiki  # 使用wiki布局模板
wiki: hexo_stellar # 这是项目名
menu_id: wiki
title: 文章部署流程
date: 2024-08-07 13:40:22 
banner: /assets/cover/cover_okr.png
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
{% copy git pull prefix:$ %}
<!-- node 第四步 -->
在项目的`source/_post`文件夹下创建一个md格式文件，如`日记.md`，在日记.md文件中编辑文章内容，ctrl+s保存
<!-- node 第五步(非必要) -->
执行如下命令，查看本地文件与云端文件的差别
{% copy git status prefix:$ %}
会显示 add: 日记.md
<!-- node 第六步 -->
分别按顺序执行如下命令，将本地新建的文章文件上传到云端
{% copy git add * prefix:$ %}
{% copy git commit -m "提交更新内容，可自定义填写" prefix:$ %}
{% copy git push prefix:$ %}  

- 注意自定义内容有引号：`git commit -m '提交更新内容，可自定义填写'`

{% endtimeline %}
