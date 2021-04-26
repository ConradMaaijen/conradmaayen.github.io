---
layout: page
title: Site Index
permalink: /site-index/
---

{% for category in site.categories %}
<h3 class="capitalized_category">{{ category[0] }}</h3>
<ul>
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    {% for post in category[1] %}
    <li>{{ post.date | date: date_format }} . <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
{% endfor %}
