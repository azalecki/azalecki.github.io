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
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}
.pswp-gallery img {
  width: 500px;
  max-width: 100%;
  height: auto;
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
     data-pswp-width="1650"
     data-pswp-height="2550"
     target="_blank">
    <img src="/assets/img/vtform/ruralforms_low.png" alt="Map Vermont Town Figure Grounds" />
    <span class="pswp-caption-content">
      <strong>Map Vermont Town Figure Grounds</strong><br>
      Your caption text here: what the map shows, data sources, tools used.
    </span>
  </a>

</div>

<script type="module">
  import PhotoSwipeLightbox from 'https://unpkg.com/photoswipe@5/dist/photosw
</script>
