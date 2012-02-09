---
layout: page
title: Another Hole on Git(Hub)
---
{% include JB/setup %}

### Just another site setuped by oppih using Jekyll-bootstrap :)
    
## Recent Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

Complete usage and documentation available at: [Jekyll Bootstrap](http://jekyllbootstrap.com)
