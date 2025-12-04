---
layout: page
title: Illustrating GIS Concepts
description: 
img: assets/img/thumbnails/balancedDesign_crop.png
importance: 4
category: fun
---

<link rel="stylesheet" href="https://unpkg.com/photoswipe@5/dist/photoswipe.css">

<div class="pswp-gallery pswp-gallery--single-column" id="gallery--gisart">

  <!-- badFG -->
  <a href="/assets/img/gisart/badFG.png"
     data-pswp-width="1000"  <!-- replace with actual width -->
     data-pswp-height="1000" <!-- replace with actual height -->
  >
    <img src="/assets/img/gisart/badFG.png" alt="badFG" />
  </a>

  <!-- balancedDesign -->
  <a href="/assets/img/gisart/balancedDesign.png"
     data-pswp-width="1000"
     data-pswp-height="1000"
  >
    <img src="/assets/img/gisart/balancedDesign.png" alt="balancedDesign" />
  </a>

  <!-- Dev_Surf_Secant -->
  <a href="/assets/img/gisart/Dev_Surf_Secant.png"
     data-pswp-width="1000"
     data-pswp-height="1000"
  >
    <img src="/assets/img/gisart/Dev_Surf_Secant.png" alt="Dev_Surf_Secant" />
  </a>

  <!-- goodFG -->
  <a href="/assets/img/gisart/goodFG.png"
     data-pswp-width="1000"
     data-pswp-height="1000"
  >
    <img src="/assets/img/gisart/goodFG.png" alt="goodFG" />
  </a>

  <!-- maup -->
  <a href="/assets/img/gisart/maup.png"
     data-pswp-width="1000"
     data-pswp-height="1000"
  >
    <img src="/assets/img/gisart/maup.png" alt="maup" />
  </a>

  <!-- measureLat -->
  <a href="/assets/img/gisart/measureLat.png"
     data-pswp-width="1000"
     data-pswp-height="1000"
  >
    <img src="/assets/img/gisart/measureLat.png" alt="measureLat" />
  </a>

  <!-- measureLong -->
  <a href="/assets/img/gisart/measureLong.png"
     data-pswp-width="1000"
     data-pswp-height="1000"
  >
    <img src="/assets/img/gisart/measureLong.png" alt="measureLong" />
  </a>

</div>

<script type="module">
  import PhotoSwipeLightbox from 'https://unpkg.com/photoswipe@5/dist/photoswipe-lightbox.esm.min.js';
  import PhotoSwipe from 'https://unpkg.com/photoswipe@5/dist/photoswipe.esm.min.js';

  const lightbox = new PhotoSwipeLightbox({
    gallery: '#gallery--gisart',
    children: 'a',
    pswpModule: PhotoSwipe
  });

  lightbox.init();
</script>
