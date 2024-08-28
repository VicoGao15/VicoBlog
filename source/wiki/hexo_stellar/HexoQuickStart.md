---
layout: wiki  # 使用wiki布局模板
wiki: hexo_stellar # 这是项目名
menu_id: wiki
title: Hexo常用命令和功能
date: 2024-08-07 13:30:22
tags: 
  - Hexo
categories: 
  - 教程
---
Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).

## 快速开始

### 创建文章

``` bash
$ hexo new "My New Post"
```
在新建文章时，Hexo 会根据 scaffolds 文件夹内相对应的文章模板来建立文件。

``` bash
$ hexo new <模板> "文章文件名称"
```

更多内容: [Writing](https://hexo.io/docs/writing.html)

### 本地启动服务

``` bash
$ hexo server
$ hexo s
```

更多内容: [Server](https://hexo.io/docs/server.html)

### 生成静态文件

``` bash
$ hexo generate
$ hexo g
```

更多内容: [Generating](https://hexo.io/docs/generating.html)

### 部署到远程站点(需要配置一键部署)

``` bash
$ hexo deploy
$ hexo d
```
更多内容: [Deployment](https://hexo.io/docs/one-command-deployment.html)
### 一键部署
 *前提：本地配置好SSL连接*  
安装 hexo-deployer-git： 
``` bash
$ npm i hexo-deployer-git --save
```
在 _config.yml 中添加以下配置（如果配置已经存在，请将其替换为如下）:
``` bash
deploy:
  type: git
  repo: https://github.com/<username>/<project>
  # example, https://github.com/VicoBlog/vicoblog.github.io
  branch: main
  message: [提交信息]
```
执行 hexo clean && hexo deploy 。
浏览 username.github.io，检查你的网站能否运作。
### 使用 Markdown 嵌入图片
[hexo-renderer-marked](https://github.com/hexojs/hexo-renderer-marked) 3.1.0 引入了一个新的选项，可以在 markdown 中嵌入图片。  

安装hexo-renderer-marked：
``` bash
$ npm install hexo-renderer-marked --save
```
如需启用：
``` bash
_config.yml
post_asset_folder: true
marked:
  prependRoot: true
  postAsset: true
```
设置完后用hexo new "文章标题"创建文章时会自动创建一个同名的文件夹，用于存放资源文件，一定要用这个方法创建文章。使用`![]()`方法必须将图片放在新建文件时生成的同名文件夹目录下，然后在编辑器中使用以下命令格式即可添加图片：
java 代码解读复制代码  
```
![图片描述](image.png) // 这里的图片路径直接填图片名即可，不需要在添加其它目录
```

启用后，资源图片将会被自动解析为其对应文章的路径。 例如： image.jpg 位置为 /2020/01/02/foo/image.jpg ，这表示它是 /2020/01/02/foo/ 文章的一张资源图片， `![image](image.jpg)` 将会被解析为 
`<img src="/2020/01/02/foo/image.jpg">` 。

### 图片懒加载
图片懒加载是提升网站性能和用户体验的一个非常很好方式，并且几乎所有的大型网站都使用到了，比如微博，仅把用户可见的部分显示图片，其余的都暂时不加载，做法就是：让所有图片元素src指向一个小的站位图片比如loading，并新增一个属性(如data-original)存放真实图片地址。每当页面加载（或者滚动条滚动），使用JS脚本将可视区域内的图片src替换回真实地址，并做请求重新加载。  
```
$ npm install hexo-lazyload-image --save
```
_config.yml配置文件添加：  
```
lazyload:
  enable: true  # 是否开启图片懒加载
  onlypost: false  # 是否只对文章的图片做懒加载
  loadingImg: # eg ./images/loading.gif
  isSPA: true  # 必须
```  

### 页脚添加运行时间
- 第一步：stellar主题的_config.yml 文件下，找到  footer ,在 content: 之后添加代码。
- 第二步：修改 X 部分的时间，改成自己网站成立的年月日即可。
```
  content: | # 支持 Markdown 格式
    落霞与孤鹜齐飞，秋水共长天一色。
    本站由 **[{author.name}](https://github.com/VicoGao15)** 使用 **[{theme.name} {theme.version}]({theme.tree})** 主题创建。
    <script type="text/javascript">
    function show_runtime() {
        window.setTimeout("show_runtime()", 1000);
        X = new Date("8/15/2024 00:00:00");
        Y = new Date();
        T = (Y.getTime() - X.getTime());
        M = 24 * 60 * 60 * 1000;
        a = T / M;
        A = Math.floor(a);
        b = (a - A) * 24;
        B = Math.floor(b);
        c = (b - B) * 60;
        C = Math.floor((b - B) * 60);
        D = Math.floor((c - C) * 60);
        runtime_span.innerHTML = "⏲️本站已运行 " + A + "天 " + B + "小时 " + C + "分 " + D + "秒⏲️"
    }
    show_runtime();
    </script>
    <span id="runtime_span"></span>
    ```
