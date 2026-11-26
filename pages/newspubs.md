---
title: News & Publications
layout: page
permalink: /news-publications/
---

<div class="grid-container">
<div class="grid-x grid-padding-x">

<!-- COLUMN 1: Recent Posts -->
<div class="medium-12 large-8 cell">
<h2>Recent News</h2>

{% if site.posts.size > 0 %}
<div class="post-list margin-bottom-large">
{% for post in site.posts limit: 5 %}
<article class="margin-bottom-medium padding-bottom-xsmall border-bottom-lightgray">
<h3 class="h5 margin-bottom-xxsmall">
<a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
</h3>
<p class="text-muted">{{ post.date | date: "%B %d, %Y" }}</p>
{% if post.excerpt %}
<p class="text-small">{{ post.excerpt | strip_html | truncatewords: 25 }}</p>
{% endif %}
</article>
{% endfor %}
</div>
{% else %}
<p>No recent posts found.</p>
{% endif %}

<div class="text-right">
<a href="{{ site.baseurl }}/news/" class="button hollow secondary">View All News</a>
</div>
</div>

<!-- COLUMN 2: Recent Publications -->
<div class="medium-12 large-4 cell">
<h2>Most Recent Publications & Presentations</h2>

{% assign itemsSorted = site.data.publications | sort: "date" | reverse %}
{% if itemsSorted.size > 0 %}
<div class="publications-list">
{% for item in itemsSorted limit: 5 %}
{% capture citationoutput %}{{item.citation}}{%- if item.doi != blank %} DOI: <a href="{{ item.doi }}">{{ item.doi }}</a>.{% endif %} {%- if item.link != blank %} <a href="{{ item.link }}">{{ item.link }}</a>.{% endif %}{% endcapture %}
{{ citationoutput  | markdownify }}
{% endfor %}
</div>
{% endif %}

<div class="text-right">
<a href="{{ site.baseurl }}/publications/" class="button hollow secondary">View All Publications</a>
</div>
</div>

</div><!-- /grid-x -->
</div><!-- /grid-container -->
