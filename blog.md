---
title: Blog Posts
permalink: /blog/
---

# Blog Posts

<nav style="margin: 20px 0; padding: 10px 0; border-bottom: 1px solid #e1e4e8;">
  <a href="{{ site.baseurl }}/">Home</a> | <strong><a href="{{ site.baseurl }}/blog/">Blog Posts</a></strong>
</nav>

Welcome to my blog! Here you'll find posts about Product Management, strategy, and what I'm learning along the way.

---

{% for post in site.posts %}
  <h2>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </h2>
  <p><em>{{ post.date | date: "%B %-d, %Y" }}</em></p>
  {% comment %} Use explicit excerpt from front matter if available, otherwise use content {% endcomment %}
  {% if post.excerpt %}
    {% assign raw_excerpt = post.excerpt %}
  {% else %}
    {% assign raw_excerpt = post.content %}
  {% endif %}
  {% comment %} Strip all HTML tags and clean up whitespace {% endcomment %}
  {% assign text_only = raw_excerpt | strip_html | replace: '&nbsp;', ' ' | normalize_whitespace | strip %}
  <p>{{ text_only | truncatewords: 50 }}</p>
  <hr>
{% endfor %}

