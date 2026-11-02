---
layout: page
title: Commissioned
description: Projects that come from someone else's brain
img: assets/img/thumbnails/forestpreserve_crop.png
importance: 6
category: maps
---

<link rel="stylesheet" href="https://unpkg.com/photoswipe@5/dist/photoswipe.css">
<link rel="stylesheet" href="https://unpkg.com/photoswipe-dynamic-caption-plugin/photoswipe-dynamic-caption-plugin.css">

<style>
.pswp-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 15px;
  align-items: start;
  margin-bottom: 2rem; /* space between a gallery and the next heading */
}
.pswp-gallery a {
  display: block;
}
.pswp-gallery img {
  width: 100%;
  aspect-ratio: 1/1;
  object-fit: cover;
  object-position: top;
  border-radius: 4px;
  display: block;
}
.pswp-caption-content {
  display: none;
}
</style>


## Mapping Middlebury College Lands

<div class="pswp-gallery">

  <a href="/assets/img/collegelands/ChipmanHill_medium.png"
     data-pswp-width="3000" data-pswp-height="2120" data-cropped="true"
     target="_blank">
    <img src="/assets/img/collegelands/ChipmanHill_medium.png" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

  <a href="/assets/img/collegelands/_medium_.png"
     data-pswp-width="2120" data-pswp-height="3000" data-cropped="true"
     target="_blank">
    <img src="/assets/img/collegelands/LussierFarm_medium.png" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

  <a href="/assets/img/collegelands/QuesnelFarm_medium.png"
     data-pswp-width="2120" data-pswp-height="3000" data-cropped="true"
     target="_blank">
    <img src="/assets/img/collegelands/QuesnelFarm_medium.png" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>


</div>

## American Steamboats in Nicaragua

<div class="pswp-gallery">

  <a href="/assets/img/shipwrecks/NicaraguaRoute.png"
     data-pswp-width="3509" data-pswp-height="2480" data-cropped="true"
     target="_blank">
    <img src="/assets/img/shipwrecks/NicaraguaRoute.png" alt="Description of image 1" />
    <span class="pswp-caption-content">
      <strong>Image 1 title</strong><br>Caption text here.
    </span>
  </a>

  <a href="/assets/img/shipwrecks/RioSanJuan.png"
     data-pswp-width="3334" data-pswp-height="1917" data-cropped="true"
     target="_blank">
    <img src="/assets/img/shipwrecks/RioSanJuan.png" alt="Description of image 2" />
    <span class="pswp-caption-content">
      <strong>Image 2 title</strong><br>Caption text here.
    </span>
  </a>

</div>


## Atlas of Globalization

The [Middlebury Atlas of Globalization](https://www.langenscheidt.com/shop/englisch/middlebury-atlas-of-globalization-SW50013?srsltid=AfmBOoqcND4qE6kT0WviLjYcHgRB_k4lP0jtJYCV7HFWz9MuA521LBOc) is an atlas textbook for college level introductory courses in international and global studies. The atlas was authored by three Middlebury College professors and explores the process of globalization through various academic disciplines like history, political science and environmental studies. The atlas includes over 100 maps, atleast 50 of which I had the pleasure of helping produce. 

I joined the "Global Atlas Team" as a cartographer/research assistant tasked with exploring and mapping topics such as military spending, flows of capital, religious affiliation. Below is a selection of some of the maps I contributed to.

<div class="pswp-gallery">

  <a href="/assets/img/atlas/covidcases_medium.png"
     data-pswp-width="2000" data-pswp-height="3000" data-cropped="true"
     target="_blank">
    <img src="/assets/img/atlas/covidcases_medium.png" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

  <a href="/assets/img/atlas/euromigration_medium.png"
     data-pswp-width="2000" data-pswp-height="3000" data-cropped="true"
     target="_blank">
    <img src="/assets/img/atlas/euromigration_medium.png" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

  <a href="/assets/img/atlas/waterpollution_medium.png"
     data-pswp-width="2000" data-pswp-height="3000" data-cropped="true"
     target="_blank">
    <img src="/assets/img/atlas/waterpollution_medium.png" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

  <a href="/assets/img/atlas/religion_medium.png"
     data-pswp-width="2000" data-pswp-height="3000" data-cropped="true"
     target="_blank">
    <img src="/assets/img/atlas/religion_medium.png" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

</div>

<script type="module">
  import PhotoSwipeLightbox from 'https://unpkg.com/photoswipe@5/dist/photoswipe-lightbox.esm.min.js';
  import PhotoSwipe from 'https://unpkg.com/photoswipe@5/dist/photoswipe.esm.min.js';
  import PhotoSwipeDynamicCaption from 'https://unpkg.com/photoswipe-dynamic-caption-plugin/photoswipe-dynamic-caption-plugin.esm.js';

  const lightbox = new PhotoSwipeLightbox({
    gallery: '.pswp-gallery',   // class selector: every matching div becomes its own gallery
    children: 'a',
    pswpModule: PhotoSwipe
  });

  const captionPlugin = new PhotoSwipeDynamicCaption(lightbox, {
    type: 'auto'
  });

  lightbox.init();
</script>