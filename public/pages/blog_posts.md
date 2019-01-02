---
layout: page
title: Todas as postagens
---

<div>
    {% for post in site.posts %}    
        <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
        <p><small><strong>{{ post.date | date: "%B %e, %Y" }}</strong></small></p>
        <!-- This post listing code snippet was taken from:
        https://gist.github.com/erjjones/1998382 -->
    {% endfor %}
<div>

