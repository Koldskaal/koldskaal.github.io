---
layout: default
title: Archive
---

# Archive

A list of all posts on the site

{% assign postsByDate = site.posts | group_by_exp: "post", "post.date | date: '%-d %B %Y'" %}

{% for date in postsByDate %}
  <div class="archive-frame">
    {% for post in date.items %}
        <a href="{{ post.url }}" class="archive-box">

          <div class="post-title">{{ post.title }}</div>
          <div class="archive-date">{{ post.date | date: '%d-%m-%Y' }}</div>
        </a>
  {% endfor %}

  </div>
{% endfor %}
