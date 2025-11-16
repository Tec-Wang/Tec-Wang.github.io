---
layout: default
title: Home
---

{% if site.avatar %}
![头像]({{ site.avatar }}){: .avatar}
{% endif %}

# {{ site.title }}

{{ site.description }}

---

## 📚 文章分类

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
