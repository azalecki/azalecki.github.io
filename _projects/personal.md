---
layout: page
title: Personal Projects
description: Here you will find projects that I have made because I wanted to make them (not because someone else wanted me to make them).
img: assets/img/thumbnails/forestpreserve_crop.png
importance: 6
category: cartography
---

<link rel="stylesheet" href="https://unpkg.com/photoswipe@5/dist/photoswipe.css">
<link rel="stylesheet" href="https://unpkg.com/photoswipe-dynamic-caption-plugin/photoswipe-dynamic-caption-plugin.css">

<style>
.pswp-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 15px;
  align-items: start; /* keeps short images from stretching to match tall ones */
}
.pswp-gallery a {
  display: block;
}
.pswp-gallery img {
  width: 100%;
  aspect-ratio: 4 / 5;      /* thumbnail shape: change to 1 / 1, 4 / 3, etc. */
  object-fit: cover;        /* crops to fill the shape instead of squishing */
  object-position: top;     /* keeps the top of each map (title area) visible */
  border-radius: 4px;
  display: block;
}
/* Captions live in the HTML but are only shown inside the lightbox */
.pswp-caption-content {
  display: none;
}
</style>

<div class="pswp-gallery" id="gallery--personal">

  <a href="/assets/img/burlington/novacancies_medium.png"
     data-pswp-width="2900"
     data-pswp-height="4161"
     target="_blank">
    <img src="/assets/img/burlington/novacancies_low.png" alt="Sorry, No Vacancies: A Geography of Burlington's Housing Crisis" />
    <span class="pswp-caption-content">
      <strong>Sorry, No Vacancies: A Geography of Burlington's Housing Crisis</strong><br>
      Your caption text here: what the map shows, data sources, tools used.
    </span>
  </a>

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

  <a href="/assets/img/other/southhero_medium.png"
     data-pswp-width="1650"
     data-pswp-height="2550"
     target="_blank">
    <img src="/assets/img/other/southhero_low.png" alt="Map of South Hero Island, Vermont" />
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

  <a href="/assets/img/other/UndertheTexasSun.jpg"
     data-pswp-width="2576"
     data-pswp-height="1503"
     target="_blank">
    <img src="/assets/img/other/UndertheTexasSun_low.jpg" alt="Under the Texas Sun" />
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