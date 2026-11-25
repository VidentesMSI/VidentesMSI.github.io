---
title: About Videntes and Multi Spectral Imaging
layout: page
permalink: /about/
---

## What is Multispectral Imaging?

Imagine being able to see the invisible, uncovering secrets of medieval artifacts, manuscripts, and paintings that have been hidden for centuries. This innovative technology uses different wavelengths of light to peer beneath the surface of cultural treasures, revealing fascinating details that our eyes alone can’t see. It’s like having a time machine at our fingertips, allowing us to journey back through history and witness the early versions, hidden texts, and lost artistry of creations from another time.

In Videntes, we harness the power of multispectral imaging to breathe new life into historical texts. This isn’t just about looking at old objects in a new light; it’s about rewriting history with a more accurate, vibrant brush. Whether it’s unearthing a forgotten poem on the back of an ancient manuscript or discovering the original contents of a centuries-old drawing, multispectral imaging opens up a world of possibilities. It’s not just technology; it’s a gateway to the past, inviting everyone to be a detective in the grand mystery of human history. Join us as we embark on this thrilling adventure, using cutting-edge tools to uncover the stories that time almost erased!

<div class="orbit" role="region" aria-label="Leeds 2025 MSI Workshop In Action" data-orbit="ble6ev-orbit" data-resize="37lpn6-orbit" id="37lpn6-orbit" data-events="resize">

<div class="orbit-wrapper">
<div class="orbit-controls">
<button class="orbit-previous" tabindex="0"><span class="show-for-sr">Previous Slide</span>◀︎</button>
<button class="orbit-next" tabindex="0"><span class="show-for-sr">Next Slide</span>▶︎</button>
</div>

<ul class="orbit-container" tabindex="0" style="height: 784px;">
<li class="orbit-slide" data-slide="0" is-active="" style="display: none;">
<figure class="orbit-figure">
<img class="orbit-image" src="{{site.urlimg}}TeamInAction/teamgiovanni_sylvialookingatscrolls.jpg" alt="UV Light">
<figcaption class="orbit-caption">Dr. Silvia Faccin explores the Vercelli scrolls with other member of the Videntes team</figcaption>
</figure>
</li>


<li class="orbit-slide" data-slide="1" style="display: none;">
<figure class="orbit-figure">
<img class="orbit-image" src="{{site.urlimg}}TeamInAction/helen_heather_software.jpg" alt="Davies Wacha">
<figcaption class="orbit-caption">Helen Davies and Heather Wacha work with Digital Mappa data</figcaption>
</figure>
</li>

<li class="orbit-slide is-active" data-slide="2" style="display: block;" aria-live="polite">
<figure class="orbit-figure">
<img class="orbit-image" src="{{site.urlimg}}TeamInAction/RedLightCapture.png" alt="Red-light Acta Scroll">
<figcaption class="orbit-caption">Red-light capture on the Acta scroll</figcaption>
</figure>
</li>

<li class="orbit-slide" data-slide="3" style="display: none;">
<figure class="orbit-figure">
<img class="orbit-image" src="{{site.urlimg}}TeamInAction/EnteringTheArchive.png" alt="Archive Entrance">
<figcaption class="orbit-caption">Members of the Videntes team enter the archive in Vercelli</figcaption>
</figure>
</li>

<li class="orbit-slide" data-slide="4" style="display: none;">
<figure class="orbit-figure">
<img class="orbit-image" src="{{site.urlimg}}TeamInAction/team_imaging.jpg" alt="Light capture">
<figcaption class="orbit-caption">Members of the Videntes team running a light-capture series</figcaption>
</figure>
</li>

</ul>
</div>

<nav class="orbit-bullets">
<button data-slide="0" class=""><span class="show-for-sr">First slide details.</span></button>
<button data-slide="1" class=""><span class="show-for-sr">Second slide details.</span></button>
<button data-slide="2" class="is-active"><span class="show-for-sr">Third slide details.</span></button>
<button data-slide="3" class=""><span class="show-for-sr">Fourth slide details.</span></button>
<button data-slide="4" class=""><span class="show-for-sr">Fourth slide details.</span></button>
</nav>
</div>


### What are we seeing?

<figure>
<div class="grid-container">
<div class="grid-x grid-padding-x grid-margin-x">
<div aria-label="Digital Mappa faded" data-categories="MSI, Mappa" data-formats="document" class="cell filter-item small-12 medium-6 large-6 filter-simple-item">
<div class="card-thumbnail">
<img class="square thumbnail" src="{{site.urlimg}}Scroll/1.2_mnf2-faded-transition_.jpg" alt="">
</div>
</div>

<div aria-label="Digital Mappa faded" data-categories="MSI, PCA, Mappa" data-formats="document" class="cell filter-item small-12 medium-6 large-6 filter-simple-item">
<div class="card-thumbnail">
<img class="square thumbnail" src="{{site.urlimg}}Scroll/1.2_mnf2-faded-PCA.jpg" alt="">
</div>
</div>
<figcaption>Images of the Vercelli Mappa Mundi with side-by-side demonstrations of ink recaptured from water-damage loss using the MSI process.</figcaption></div></div></figure>


## Who are the Videntes Team?

Established in July 2022 in Vercelli (Italy), _Videntes_: A Multispectral Imaging Collective includes scholars whose academic training varies from History and Literature, to Art History and Digital Humanities. Our teaching and professional service includes secondary and higher education, libraries and special collections, and collaborations with international project-based teams. Our teaching and professional service includes secondary and higher education, libraries and special collections, and collaborations with international project-based teams. **Our name, _Videntes_ (Latin, plural for the act of seeing), is evocative of our commitment to seeing together; to looking across disciplinary boundaries and historical chronologies, and to bringing attention to the medieval processes used to make handmade books (manuscripts) and the modern technologies that can be applied to those books and their places of use, such as multispectral imaging or photogrammetry**. By seeing together we recover things lost, or unseen, and illuminate what mattered about an object in the past, argue what should matter to the present, and imagine what could matter for the future. In summer 2023 Videntes will returned to Vercelli to work in collaboration with Dr. Silvia Faccin, segratario and conservator of manuscripts for the Museo del Tesoro del Duomo e Archivio Capitolare.



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
