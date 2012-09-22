---
layout: page
title: Another Hole
tagline: about => :hacking, :drawing
---
{% include JB/setup %}

### Just another site by [oppih](http://oppih.me) :)

----
![Marcos](http://img39.ph.126.net/gqp2GUgqnJ4f0PNsVucgaw==/3148016139533681686.jpg)

[About Subcomandante Marcos](http://en.wikipedia.org/wiki/Subcomandante_Marcos)

----
## Recent Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
