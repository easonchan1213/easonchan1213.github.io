---
layout: page
title: "Notes on Kaggle competition"
description: "sharing of knowledge on some useful tricks I found in Kaggle forum threads"
---
{% include JB/setup %}
> ####sharing of knowledge on some useful tricks I found in Kaggle forum threads


<ul class="posts">
  {% for post in site.kaggles %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>