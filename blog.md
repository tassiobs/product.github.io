---
title: Blog Posts
---

# Blog Posts

<nav style="margin: 20px 0; padding: 10px 0; border-bottom: 1px solid #e1e4e8;">
  <a href="/">Home</a> | <strong><a href="/blog">Blog Posts</a></strong>
</nav>

Welcome to my blog! Here you'll find posts about Product Management, strategy, and what I'm learning along the way.

---

{% for post in site.posts %}
  <h2>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </h2>
  <p><em>{{ post.date | date: "%B %-d, %Y" }}</em></p>
  {% if post.excerpt %}
    <p>{{ post.excerpt }}</p>
  {% endif %}
  <hr>
{% endfor %}

