---
layout: page
title: Projects
customlink: /projects/




---

<div class="home">

  <ul class="post-list">
    {% for post in site.projects %}
      <li>
      

        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}{% if post.updated %} • <b>updated: </b>{{ post.updated | date_to_long_string }}{% endif %}{% if post.author %} • {{ post.author }}{% endif %}{% if post.place %} • {{ post.place }}{% endif %} </span>



        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
      </li>
    {% endfor %}
  </ul>








</div>
