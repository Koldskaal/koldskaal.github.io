---
layout: default
title: Home
---

# Archive

Browse all posts by month and year.

{% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

{% for year in postsByYear %}
  <div class="archive-frame">
  {% assign postsByMonth = year.items | group_by_exp: "post", "post.date | date: '%B'" %}
  <h2 class="archive-year">{{ year.name }}</h2>
  {% for month in postsByMonth %}
    <h4 class="archive-month">{{ month.name }}</h4>
    {% for post in month.items %}
      {% capture post_year %}{{ post.date | date: "%Y" }}{% endcapture %}
      {% capture post_day %}{{ post.date | date: "%e" }}{% endcapture %}
      {% if year.name == post_year %}
        <div class="archive-box">
          <div class="archive-day">{{ post_day }}</div>
          <div class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></div>
        </div>
      {% endif %}
    {% endfor %}
  {% endfor %}

  </div>
{% endfor %}
