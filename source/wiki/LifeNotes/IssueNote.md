---
layout: wiki  # 使用wiki布局模板
wiki: wiki-note # 这是项目名
title: 「Issue动态笔记」
date: 2024-08-16 16:47:19
banner: /assets/cover/cover_notes.jpg
banner_info: 
    subtitle: 在vicoblog/notes仓库中提交issue作为笔记，在此处展示  
comments: true
beaudar:
    repo: vicoblog/vicoblog-comments
    issue-term: pathname
    theme: preferred-color-scheme
    input-position: top # top/bottom 评论框位置
    comment-order: desc # desc 排序
    keep-theme: # true/false
    loading: false
    branch: main
repo: vicoblog/notes
---

{% tabs %}
<!-- tab 日常笔记 -->
{% timeline api:https://api.github.com/repos/vicoblog/notes/issues?per_page=10&labels=note %}{% endtimeline %}
<!-- tab 技术笔记 -->
{% timeline api:https://api.github.com/repos/vicoblog/notes/issues?per_page=10&labels=technology&accept=%27Bearer%20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%27 %}{% endtimeline %}
{% endtabs %}
