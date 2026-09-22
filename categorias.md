---
layout: single
title: Categorías
permalink: /categorias/
author_profile: false
---

{% assign cat_names = "" | split: "," %}
{% for pair in site.categories %}
{% assign cat_names = cat_names | push: pair[0] %}
{% endfor %}
{% assign cat_names = cat_names | sort_natural %}

<ul class="fcc-chip-list">
{% for cat_name in cat_names %}
{% assign posts_for_cat = site.categories[cat_name] %}
{% assign chip_index = site.data.categories[cat_name] | default: 5 %}
<li><a href="{{ site.category_archive.path | relative_url }}{{ cat_name | slugify }}/" class="fcc-chip fcc-chip-{{ chip_index }}" rel="tag">{{ cat_name }} ({{ posts_for_cat.size }})</a></li>
{% endfor %}
</ul>
