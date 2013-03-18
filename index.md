---
layout: page
title: Stuff I learned...
tagline: Notes and thoughts (mostly on software)
---
{% include JB/setup %}

<ul class="posts">
  {% assign post_date = '' %}
  {% for post in site.posts %}
    {% if post.date != post_date %}
    {% assign post_date = post.date %}
    <h4>{{ post.date | date_to_string }}</h4>
    {% endif %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
