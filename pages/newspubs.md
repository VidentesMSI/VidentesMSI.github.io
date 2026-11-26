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
{% assign img = post.image %}
{% assign image_src = "" %}
{% assign image_credit = "" %}

{% if img and img.src %}
{% assign raw_src = img.src | replace_first: ' ', '' %}
{% assign resolved_src = raw_src %}

<!-- Auto-prepend /assets/img/posts/ for local files -->
{% unless raw_src contains "://" %}
{% assign resolved_src = "/assets/img/posts/" | append: raw_src %}
{% endunless %}

<!-- Safely handle site.baseurl without breaking external URLs -->
{% if resolved_src contains "://" %}
{% assign image_src = resolved_src %}
{% else %}
{% assign image_src = site.baseurl | append: resolved_src %}
{% endif %}

{% if img.credit %}{% assign image_credit = img.credit %}{% endif %}
{% endif %}

<article class="post-item margin-bottom-medium padding-bottom-xsmall border-bottom-lightgray" style="display: flex; align-items: flex-start; gap: 1rem;">
<!-- Image or Fallback Placeholder (Square Crop) -->
{% if image_src != "" %}
<img src="{{ image_src }}" alt="" loading="lazy" class="post-thumb flex-shrink-0" 
style="width: 120px; height: 120px; object-fit: cover; border-radius: 4px;">
{% else %}
<div class="placeholder-img flex-shrink-0" 
style="width: 120px; height: 120px; background: #f8f9fa; border: 2px dashed #ced4da; border-radius: 4px; display: flex; align-items: center; justify-content: center;">
<i class="fa fa-newspaper-o" style="color: #6c757d;"></i>
</div>
{% endif %}

<!-- Post Content -->
<div class="post-text flex-grow-1 min-width-0">
<h3 class="h5 margin-bottom-xxsmall">
<a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
</h3>
<p class="text-muted">{{ post.date | date: "%B %d, %Y" }}</p>

{% if post.excerpt %}
<p class="text-small">{{ post.excerpt | strip_html | truncatewords: 25 }}</p>
{% endif %}

<!-- Image Credit (List View Only) -->
{% if image_credit != "" %}
<p class="image-credit text-xsmall text-muted" style="margin-top: 0.4rem; font-style: italic;">📷 {{ image_credit }}</p>
{% endif %}
</div>
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
