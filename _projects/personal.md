---
layout: page
title: Personal
description: Projects that come from my brain
img: assets/img/thumbnails/forestpreserve_crop.png
importance: 6
category: maps
---

<link rel="stylesheet" href="https://unpkg.com/photoswipe@5/dist/photoswipe.css">
<link rel="stylesheet" href="https://unpkg.com/photoswipe-dynamic-caption-plugin/photoswipe-dynamic-caption-plugin.css">

<style>
.pswp-gallery {
  column-width: 200px;   /* as many ~260px columns as fit: 3 on desktop, 2 on tablet, 1 on phone */
  column-gap: 15px;
}
.pswp-gallery a {
  display: block;
  margin-bottom: 15px;
  break-inside: avoid;   /* keeps each image from splitting across columns */
}
.pswp-gallery img {
  width: 100%;
  height: auto;          /* natural aspect ratio, no cropping */
  border-radius: 4px;
  display: block;
}
/* Captions live in the HTML but are only shown inside the lightbox */
.pswp-caption-content {
  display: none;
}
</style>

<div class="pswp-gallery" id="gallery--personal">

  <a href="/assets/img/forestpreserves/ForestPreservesoftheFarNorthwestSide_medium.png"
     data-pswp-width="1950"
     data-pswp-height="6600"
     target="_blank">
    <img src="/assets/img/forestpreserves/ForestPreservesoftheFarNorthwestSide_low.png" alt="Map of the forest preserves of the Far Northwest Side, Chicago" />
    <span class="pswp-caption-content">
      <strong>Forest Preserves of the Far Northwest Side</strong><br>
      Your caption text here: what the map shows, data sources, tools used.
    </span>
  </a>

  <a href="/assets/img/burlington/Burlington_medium.png"
     data-pswp-width="2900"
     data-pswp-height="4161"
     target="_blank">
    <img src="/assets/img/burlington/Burlington_low.png" alt="Sorry, No Vacancies: A Geography of Burlington's Housing Crisis" />
    <span class="pswp-caption-content">
      <strong>Sorry, No Vacancies: A Geography of Burlington's Housing Crisis</strong><br>
      Your caption text here: what the map shows, data sources, tools used.
    </span>
  </a>

  <a href="/assets/img/southhero/southhero_medium.png"
     data-pswp-width="1650"
     data-pswp-height="2550"
     target="_blank">
    <img src="/assets/img/southhero/southhero_low.png" alt="Map of South Hero Island, Vermont" />
    <span class="pswp-caption-content">
      <strong>Map of South Hero Island, Vermont</strong><br>
      Your caption text here: what the map shows, data sources, tools used.
    </span>
  </a>

  <a href="/assets/img/vtform/ruralforms_medium.png"
     data-pswp-width="2700"
     data-pswp-height="4500"
     target="_blank">
    <img src="/assets/img/vtform/ruralforms_low.png" alt="Map Vermont Town Figure Grounds" />
    <span class="pswp-caption-content">
      <strong>Map Vermont Town Figure Grounds</strong><br>
      Your caption text here: what the map shows, data sources, tools used.
    </span>
  </a>

  <a href="/assets/img/cmnd/cmnd_medium.png"
     data-pswp-width="5000"
     data-pswp-height="3256"
     target="_blank">
    <img src="/assets/img/cmnd/cmnd_low.png" alt="The Coal Mine Next Door" />
    <span class="pswp-caption-content">
      <strong>The Coal Mine Next Door</strong><br>
      Your caption text here: what the map shows, data sources, tools used.
    </span>
  </a>

  <a href="/assets/img/texassun/UndertheTexasSun.jpg"
     data-pswp-width="2576"
     data-pswp-height="1503"
     target="_blank">
    <img src="/assets/img/texassun/UndertheTexasSun_low.jpg" alt="Under the Texas Sun" />
    <span class="pswp-caption-content">
      <strong>Under the Texas Sun</strong><br>
      Your caption text here: what the map shows, data sources, tools used.
    </span>
  </a>

</div>

<script type="module">
  import PhotoSwipeLightbox from 'https://unpkg.com/photoswipe@5/dist/photoswipe-lightbox.esm.min.js';
  import PhotoSwipe from 'https://unpkg.com/photoswipe@5/dist/photoswipe.esm.min.js';
  import PhotoSwipeDynamicCaption from 'https://unpkg.com/photoswipe-dynamic-caption-plugin/photoswipe-dynamic-caption-plugin.esm.js';

  const lightbox = new PhotoSwipeLightbox({
    gallery: '#gallery--personal',
    children: 'a',
    pswpModule: PhotoSwipe
  });

  // Caption plugin (must be added before lightbox.init())
  const captionPlugin = new PhotoSwipeDynamicCaption(lightbox, {
    type: 'auto'
  });

  lightbox.init();
</script>