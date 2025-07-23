---
layout: home
title: 首页
---

# 欢迎来到我的技术网站 2025年07月23日

这是一个使用Jekyll构建的简单美观的网站。

## 最新文章

{% for post in site.posts limit:3 %}
### [{{ post.title }}]({{ post.url }})
{{ post.date | date: "%Y年%m月%d日" }}
{{ post.excerpt }}
{% endfor %}

[查看所有文章 →]({{ site.baseurl }}/posts/)
