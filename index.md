---
layout: default
title: My Bookmarks
permalink: /
---

# Bookmarks

{% assign bookmarks = site.pages | where: "layout", "bookmark" | sort: "path" | reverse %}

<ul>
{% for b in bookmarks %}
  <li>
    <a href="{{ b.url | relative_url }}">{{ b.title | default: b.path }}</a>
    {% if b.source_url %}
      — <small><a href="{{ b.source_url }}" target="_blank">source</a></small>
    {% endif %}
    {% if b.tag %}
      <br><small>{{ b.tag }}</small>
    {% endif %}
  </li>
{% endfor %}
</ul>

<p>{{ bookmarks.size }} bookmark(s)</p>