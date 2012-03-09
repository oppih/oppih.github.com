---
layout: page
title: Another Hole
tagline: Supporting tagline
---
{% include JB/setup %}

### Just another site by [oppih](http://oppih.me) :)

![Marcos](http://upload.wikimedia.org/wikipedia/commons/3/3a/Subcomandante_Marcos.jpg)
[About Subcomandante Marcos](http://ast.wikipedia.org/wiki/Subcomandante_Marcos)

## Recent Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
