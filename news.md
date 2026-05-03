---
layout: default
title: News
permalink: /news/
---

# News

{% assign sorted = site.data.news | sort: "start" | reverse %}
{% assign grouped = sorted | group_by_exp: "item", "item.start | slice: 0, 4" %}

{% for year in grouped %}
## {{ year.name }}

<hr>

{% for item in year.items %}
**{{ item.title }}**
<br>
{% if item.end %}{{ item.start | date: "%b %d, %Y" }} – {{ item.end | date: "%b %d, %Y" }}{% else %}{{ item.start | date: "%b %d, %Y" }}{% endif %}
{%if item.location%}*{{item.location}}*{% endif %}
{% if item.description %}<br>{{ item.description }}{% endif %}

---

{% endfor %}
{% endfor %}
