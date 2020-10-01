---
layout: page
title: Tags
header: Posts By Tag
---

<div class="page-heading">
<h1>{{ page.title }} </h1>
</div>

<h2> Tag List</h2>
<p>
{% for tag in site.tags %}

 <a href="#{{ tag[0] }}"> {{ tag[0] }}</a>,
 
{% endfor %}
</p>

<h4>testh5</h4>

{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3><a id="{{ tag[0] }}">
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}


<h4>testh4</h4>

{% comment %}
=======================
The purpose of this snippet is to list all the tags you have in your site.
=======================
{% endcomment %}


<h4>testh5</h4>

{% comment %}
=======================
The purpose of this snippet is to list all your posts posted with a certain tag.
=======================
{% endcomment %}
{% for tag in tags %}
	<h2 id="{{ tag | slugify }}">{{ tag }}</h2>
	<ul>
	 {% for post in site.posts %}
		 {% if post.tags contains tag %}
		 <li>
		 <h3>
		 <a href="{{ post.url }}">
		 {{ post.title }}
		 <small>{{ post.date | date_to_string }}</small>
		 </a>
		 {% for tag in post.tags %}
			 <a class="tag" href="/blog/tag/#{{ tag | slugify }}">{{ tag }}</a>
		 {% endfor %}
		 </h3>
		 </li>
		 {% endif %}
	 {% endfor %}
	</ul>
{% endfor %}






