---
title: News & Publications
layout: page
permalink: /news/
---

# News

{::nomarkdown}
{% include _postlist.html %}
{:/nomarkdown}

# Publications

{% assign types = "Monograph,Article,Conference paper,Workshop,Grant" | split: "," %}
{% for t in types %}
  {% assign itemsSorted = site.data.publications | where: 'type', t | sort: "date" | reverse %}
  {% if itemsSorted.size > 0 %}
    <h3>{{ t }}{% unless t == "Monograph" %}s{% endunless %}</h3>
    {% assign previous_i = nil %}
    {% for item in itemsSorted %}
      {% include _citation.html %}
    {% endfor %}
  {% endif %}
{% endfor %}
