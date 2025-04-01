---
layout: wiki  # 使用wiki布局模板
wiki: hexo_stellar # 这是项目名
menu_id: wiki
title: Stellar主题美化配置
date: 2024-08-028 10:55:22
tags: 
  - Hexo
  - Stellar
categories: 
  - 教程
---

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
{% link https://sumorio.com/wiki/Hexo/201Webpage-beautification.html#%E6%B7%BB%E5%8A%A0%E8%BF%90%E8%A1%8C%E6%97%B6%E9%97%B4 参考(底部添加运行时间)  %}

### Hexo插件推荐
{% link https://www.tony-bro.com/posts/2249267013/index.html Hexo插件推荐 icon:/assets/wiki/uniapp/icon.svg %}

### 使用Mermaid
Mermaid 允许你使用文本和代码创建图表和可视化。
{% link https://mermaid.nodejs.cn/intro/ 关于Mermaid icon:/assets/wiki/uniapp/icon.svg %}

### 使用Hexo-tag-map
Hexo 文章插入交互式地图！支持GoogleMap、高德地图、百度地图、Geoq地图、openstreetMap常规地图+卫星地图+卫星标注地图！一个强大的地图插件。
{% link https://github.com/kuole-o/hexo-tag-map Hexo-tag-map icon:/assets/wiki/uniapp/icon.svg %}

### 使用Echart
插件hexo-tag-echarts-new
{% link https://github.com/D-Sketon/hexo-tag-echarts-new Hexo-tag-map icon:/assets/wiki/uniapp/icon.svg %}
