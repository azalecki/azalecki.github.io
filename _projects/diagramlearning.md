---
layout: page
title: Illustrating GIS Concepts
description: 
img: assets/img/thumbnails/balancedDesign_crop.png
importance: 1
category: fun
---

{% raw %}
<!-- Add PhotoSwipe CSS -->
<link rel="stylesheet" href="https://unpkg.com/photoswipe@5/dist/photoswipe.css">

<!-- Thumbnail styling -->
<style>
.pswp-gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}

.pswp-gallery img {
  width: 450px;  /* Thumbnail width */
  height: auto;  /* Keep aspect ratio */
  border-radius: 4px; /* Optional styling */
  display: block;
}
</style>

<!-- Gallery -->
<div class="pswp-gallery pswp-gallery--single-column" id="gallery--gisart">

  <!-- badFG -->
  <a href="/assets/img/gisart/badFG.png"
     data-pswp-width="3509" 
     data-pswp-height="2480">
    <img src="/assets/img/gisart/badFG.png" alt="badFG" />
  </a>

  <!-- goodFG -->
  <a href="/assets/img/gisart/goodFG.png"
      data-pswp-width="3509"
     data-pswp-height="2480">
    <img src="/assets/img/gisart/goodFG.png" alt="goodFG" />
  </a>

   <!-- projected_multi_panel -->
  <a href="/assets/img/gisart/projected_multi_panel.png"
      data-pswp-width="2400"
     data-pswp-height="1280">
    <img src="/assets/img/gisart/projected_multi_panel.png" alt="projected_multi_panel" />
  </a>

  <!-- Dev_Surf_Secant -->
  <a href="/assets/img/gisart/Dev_Surf_Secant.png"
     data-pswp-width="2400"
     data-pswp-height="2400">
    <img src="/assets/img/gisart/Dev_Surf_Secant.png" alt="Dev_Surf_Secant" />
  </a>=

  <!-- measureLat -->
  <a href="/assets/img/gisart/measureLat.png"
     data-pswp-width="2400"
     data-pswp-height="2400">
    <img src="/assets/img/gisart/measureLat.png" alt="measureLat" />
  </a>

  <!-- measureLong -->
  <a href="/assets/img/gisart/measureLong.png"
     data-pswp-width="2400"
     data-pswp-height="2400">
    <img src="/assets/img/gisart/measureLong.png" alt="measureLong" />
  </a>

  <!-- Overlays -->
  <a href="/assets/img/gisart/overlays_all.png"
     data-pswp-width="2100"
     data-pswp-height="1500">
    <img src="/assets/img/gisart/overlays_all.png" alt="overlays_all" />
  </a>
  
  <!-- maup -->
  <a href="/assets/img/gisart/maup.png"
     data-pswp-width="2550" 
     data-pswp-height="1800">
    <img src="/assets/img/gisart/maup.png" alt="maup" />
  </a>

   <!-- balancedDesign -->
  <a href="/assets/img/gisart/balancedDesign.png"
     data-pswp-width="3236"
     data-pswp-height="2490">
    <img src="/assets/img/gisart/balancedDesign.png" alt="balancedDesign" />
  </a>

</div>

<!-- PhotoSwipe JS -->
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

{% endraw %}