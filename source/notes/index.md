---
wiki: notes
menu_id: notes
title: 「笔记」
date: 2024-08-16 16:47:19
banner: cover/notes.jpg
banner_info: 
    subtitle: 在vicoblog/notes仓库中提交issue作为笔记，在此处展示  
comments: false
beaudar:
    repo: vicoblog/vicoblog-comments
    issue-term: pathname
    theme: preferred-color-scheme
    input-position: top # top/bottom 评论框位置
    comment-order: desc # desc 排序
    keep-theme: # true/false
    loading: false
    branch: main
---

{% tabs %}
<!-- tab 最新 -->
{% timeline api:https://api.github.com/repos/vicoblog/notes/issues?direction=desc&per_page=5 %}{% endtimeline %}
<!-- tab 最多评论 -->
{% timeline api:https://api.github.com/repos/vicoblog/notes/issues?per_page=5&sort=comments %}{% endtimeline %}
<!-- tab 全部 issue -->
{% timeline api:https://api.github.com/repos/vicoblog/notes/issues: %}{% endtimeline %}
{% endtabs %}
