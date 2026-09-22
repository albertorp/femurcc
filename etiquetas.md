---
layout: single
title: Etiquetas
permalink: /etiquetas/
author_profile: false
---

{% assign tag_names = "" | split: "," %}
{% for pair in site.tags %}
{% assign tag_names = tag_names | push: pair[0] %}
{% endfor %}
{% assign tag_names = tag_names | sort_natural %}

<ul class="fcc-tag-list">
{% for tag_name in tag_names %}
{% assign posts_for_tag = site.tags[tag_name] %}
<li><a href="{{ site.tag_archive.path | relative_url }}{{ tag_name | slugify }}/">#{{ tag_name }}</a> <span class="fcc-tag-count">({{ posts_for_tag.size }})</span></li>
{% endfor %}
</ul>
