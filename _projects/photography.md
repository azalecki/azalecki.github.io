---
layout: page
title: Photography Now
description: 
img: assets/img/thumbnails/balancedDesign_crop.png
importance: 2
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

 <!-- Section heading -->
  <h4 class="gallery-heading">Studio Portrait and Still Life</h4>

<!-- Gallery -->
<div class="pswp-gallery pswp-gallery--single-column" id="gallery--photo01">

  <!-- badFG -->
  <a href="/assets/img/photography/portrait.jpg"
     data-pswp-width="3900" 
     data-pswp-height="5700">
    <img src="/assets/img/photography/portrait.jpg" alt="studio-portrait" />
  </a>

  <!-- goodFG -->
  <a href="/assets/img/photography/stilllife.jpg"
      data-pswp-width="3900"
     data-pswp-height="5700">
    <img src="/assets/img/photography/stilllife.jpg" alt="still-life" />
  </a>

<!-- Section heading -->
  <h4 class="gallery-heading">In the Style Of</h4>

  <!-- Gallery -->
<div class="pswp-gallery pswp-gallery--single-column" id="gallery--photo02">

  <!-- badFG -->
  <a href="/assets/img/photography/inthestyle1.jpg"
     data-pswp-width="2550" 
     data-pswp-height="3300">
    <img src="/assets/img/photography/inthestyle1.jpg" alt="style-plant" />
  </a>

  <!-- goodFG -->
  <a href="/assets/img/photography/inthestyle2.jpg"
      data-pswp-width="2913"
     data-pswp-height="3642">
    <img src="/assets/img/photography/inthestyle2.jpg" alt="style-portrait" />
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

