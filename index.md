---
layout: page
title: Beranda Dwijayasloka
tagline: 
---
{% include JB/setup %}
## Selamat Datang
Terima kasih atas kunjungan kamu.

## Arsip Posting
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
