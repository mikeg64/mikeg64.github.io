---
layout: page
title: Tag List
header: Posts By Tag
---
{% comment %}
<div class="page-heading">
<h1>{{ page.title }} </h1>
</div>
{% endcomment %}

<p>
{% for tag in site.tags %}

 <a href="#{{ tag[0] }}"> {{ tag[0] }}</a>,
 
{% endfor %}
</p>

<h2>Posts by Tags</h2>

{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3><a id="{{ tag[0] }}">
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}









