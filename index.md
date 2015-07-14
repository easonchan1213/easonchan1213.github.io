---
layout: page
title: Exploring Data Science
tagline: for fun
---
{% include JB/setup %}

This blog is under constructions, but I will sure be actively updating some useful information for your reference.


<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
