---
layout: page
title: Ultimos Posts
excerpt: "A short blog about human mind."
search_omit: true
ref: index
lang: es
---


<ul class="post-list">
{% assign posts=site.posts | where:"lang", page.lang %}
{% for post in posts limit:10 %}
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if post.excerpt %} <span class="excerpt">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}</a></article></li>
{% endfor %}
</ul>
