---
title: The Videntes Team
layout: page
permalink: /team/
---

![The Videntes Team]({{ site.urlimg}}TeamInAction/2022TeamPhoto.png)

(From left to right) Helen Davies, Evan Gatti, Heather Wacha, Silvia Faccin, and Katie Albers-Morris pause for a photo in the Chapter Room of the Archivio Capitolare in Vercelli, Italy Summer 2022.

{% for author in site.data.authors %}

## {{ author.display_name }}

![{{ author.display_name }} Photo]({{ site.urlimg }}{{author.avatar }})

{{ author.bio | markdownify }}

{% endfor %}
