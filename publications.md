---
layout: default
title: Publications
permalink: /publications/
---

# Publications

{% assign sorted = site.data.publications | sort: "year" | reverse %}
{% assign preprints = sorted | where: "status", "preprint" %}
{% assign published = sorted | where: "status", "published" %}

## Preprints

<hr>

{% for item in preprints %}
<i class="fa fa-file-text"></i> **{{ item.title }}**
<br>
<i class="fa fa-users"></i> {{ item.authors }}
<br>
<i class="fa fa-calendar"></i> {{ item.year }}
<br>
<i class="ai ai-arxiv"></i> [arXiv:{{ item.arxiv }}](https://arxiv.org/abs/{{ item.arxiv }})
{%- if item.doi != "" %}<br><i class="fa fa-bookmark"></i> [DOI:{{ item.doi }}](https://doi.org/{{ item.doi }}){% endif %}
{%- if item.link %}<br><i class="fa fa-link"></i> [Link]({{ item.link }}){% endif %}

---

{% endfor %}

## Published

<hr>

{% for item in published %}
<i class="fa fa-file-text"></i> **{{ item.title }}**
<br>
<i class="fa fa-users"></i> {{ item.authors }}
<br>
<i class="fa fa-book"></i> *{{ item.journal }}*, {{ item.year }}
{%- if item.arxiv %}<br><i class="ai ai-arxiv"></i> [arXiv:{{ item.arxiv }}](https://arxiv.org/abs/{{ item.arxiv }}){% endif %}
<br>
<i class="fa fa-bookmark"></i> [DOI:{{ item.doi }}](https://doi.org/{{ item.doi }})
{%- if item.link %}<br><i class="fa fa-link"></i> [Link]({{ item.link }}){% endif %}

---

{% endfor %}

