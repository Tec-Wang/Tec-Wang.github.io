---
layout: default
title: Home
---

# Welcome

欢迎来到我的网站！

这里是个人博客和项目展示站点。

## 文章分类

{% assign categories_list = site.categories | sort %}
{% for category in categories_list %}
### {{ category[0] }}

{% for post in category[1] %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y年%m月%d日" }}
{% endfor %}
{% endfor %}

---

## 最新文章

{% for post in site.posts limit:10 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y年%m月%d日" }} | 
  {% for category in post.categories %}
    <span class="category">{{ category }}</span>
  {% endfor %}
{% endfor %}
