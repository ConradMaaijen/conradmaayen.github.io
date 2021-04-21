---
layout: page
title: Site Index
permalink: /site-index/
---

{% for category in site.categories %}
    <h3 class="capitalized_category">{{ category[0] }}</h3>
    <ul>
        {% for post in category[1] %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
        {% endfor %}
    </ul>
{% endfor %}
