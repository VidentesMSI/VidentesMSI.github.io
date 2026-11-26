---
title: Videntes Publications
layout: page
permalink: /publications/
---

{% assign filtered = site.data.publications | where_exp: "item", "item.hidden != 'true'" %}
{% assign sorted = filtered | sort: "date" | reverse %}

{% if sorted.size > 0 %}
{% assign types = "" | split: ',' %}
{% for item in sorted %}
{% if item.type and item.type != blank %}
{% unless types contains item.type %}
{% assign types = types | push: item.type %}
{% endunless %}
{% endif %}
{% endfor %}

{% for pub_type in types %}
<h2>{{ pub_type }}</h2>
{% assign previous_i = "" %}

{% for item in sorted %}
{% if item.type == pub_type %}
{% assign current_i = "" %}

{% if item.status == "present" %}
{% assign current_i = "now" | date: "%Y" %}
{% elsif item.status == "in press" or item.status == "in prep" or item.status == "under review" %}
{% assign current_i = item.status %}
{% elsif item.date %}
{% assign current_i = item.date | date: "%Y" %}
{% endif %}

<div class="grid-x margin-gutters padding-gutters citation{% if current_i != previous_i %} newyear{% endif %}">
<div class="cell small-12 medium-1">
{% if current_i != previous_i %}
<h4 class="year">{{ current_i }}</h4>
{% endif %}
</div>
<div class="cell small-12 medium-11">
<!-- Auto-bold authors by display_name & display_name_alt -->
{% assign raw_cite = item.citation %}
{% for author_key in site.data.authors %}
{% assign author = site.data.authors[author_key] %}

<!-- Primary display_name -->
{% assign aname = author.display_name %}
{% if aname != blank and raw_cite contains aname %}
{% assign bold_name = '<strong>' | append: aname | append: '</strong>' %}
{% assign raw_cite = raw_cite | replace: aname, bold_name %}
{% endif %}

<!-- Alternate display_name_alt -->
{% assign alt_name = author.display_name_alt %}
{% if alt_name != blank and raw_cite contains alt_name %}
{% assign bold_name = '<strong>' | append: alt_name | append: '</strong>' %}
{% assign raw_cite = raw_cite | replace: alt_name, bold_name %}
{% endif %}
{% endfor %}

{{ raw_cite | markdownify }}
{% if item.doi != null and item.doi != "" %} DOI: <a href="{{ item.doi }}">{{ item.doi }}</a>.{% endif %}
{% if item.link != null and item.link != "" %} <a href="{{ item.link }}">{{ item.link }}</a>.{% endif %}

{% if item.description != null and item.description != "" %}
<p class="text-small text-muted">{{ item.description | markdownify }}</p>
{% endif %}
</div>
</div>

{% assign previous_i = current_i %}
{% endif %}
{% endfor %}
{% endfor %}
{% endif %}
