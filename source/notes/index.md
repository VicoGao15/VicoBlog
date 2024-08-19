---
wiki: notes
menu_id: notes
title: notes「笔记」栏目
date: 2024-08-16 16:47:19
banner: cover/notes.jpg
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
<!-- tab 全部 -->
{% timeline api:https://api.github.com/repos/vicoblog/notes/issues: %}{% endtimeline %}
<!-- tab 最新3条 -->
{% timeline api:https://api.github.com/repos/vicoblog/notes/issues?direction=desc&per_page=5 %}{% endtimeline %}
<!-- tab 最多回顾 -->
{% timeline api:https://api.github.com/repos/vicoblog/notes/issues?per_page=5&sort=comments %}{% endtimeline %}
{% endtabs %}
