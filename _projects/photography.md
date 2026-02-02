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
  <h3 class="gallery-heading">Studio Portrait and Still Life</h3>

<!-- Gallery -->
<div class="pswp-gallery pswp-gallery--single-column" id="gallery--gisart">

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