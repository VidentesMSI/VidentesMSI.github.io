---
title: The Videntes Team
layout: page
permalink: /the-videntes-team/
---

![The Videntes Team]({{ site.urlimg }}TeamInAction/2022TeamPhoto.png)

(From left to right) Helen Davies, Evan Gatti, Heather Wacha, Silvia Faccin, and Katie Albers-Morris pause for a photo in the Chapter Room of the Archivio Capitolare in Vercelli, Italy Summer 2022.

{% for author in site.data.authors %}
{% assign key = author[0] %}
{% assign data = author[1] %}

### {{ data.display_name }}
{: .bio}

![{{ data.display_name }} Photo]({{ site.urlimg }}{{ data.avatar }}){:.biophoto}

{{ data.bio | markdownify }}

{% endfor %}
