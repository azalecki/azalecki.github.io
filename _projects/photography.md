---
layout: page
title: Photography Now
description: 
img: assets/img/thumbnails/man_crop.jpg
importance: 2
category: other
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

  <a href="/assets/img/photography/portrait.jpg"
     data-pswp-width="3900" 
     data-pswp-height="5700">
    <img src="/assets/img/photography/portrait.jpg" alt="studio-portrait" />
  </a>

  <a href="/assets/img/photography/stilllife.jpg"
      data-pswp-width="3900"
     data-pswp-height="5700">
    <img src="/assets/img/photography/stilllife.jpg" alt="still-life" />
  </a>
</div>

<!-- Section heading -->
  <h4 class="gallery-heading">In the Style Of</h4>

  <!-- Gallery -->
<div class="pswp-gallery pswp-gallery--single-column" id="gallery--photo02">

  <a href="/assets/img/photography/inthestyle1.jpg"
     data-pswp-width="2550" 
     data-pswp-height="3300">
    <img src="/assets/img/photography/inthestyle1.jpg" alt="style-plant" />
  </a>

  <a href="/assets/img/photography/inthestyle2.jpg"
      data-pswp-width="2913"
     data-pswp-height="3642">
    <img src="/assets/img/photography/inthestyle2.jpg" alt="style-portrait" />
  </a>

</div>

<!-- Section heading -->
<h4 class="gallery-heading">Final Project</h4>

<!-- Gallery -->
<div class="pswp-gallery pswp-gallery--single-column" id="gallery--photo02">

  <a href="/assets/img/photography/bikes.jpg"
     data-pswp-width="2048"
     data-pswp-height="1365">
    <img src="/assets/img/photography/bikes.jpg" alt="bicycle parked on a city street" />
  </a>

  <a href="/assets/img/photography/pairwalking.jpg"
     data-pswp-width="3300"
     data-pswp-height="4950">
    <img src="/assets/img/photography/pairwalking.jpg" alt="two men walking past a pair of colorful buildings" />
  </a>

  <a href="/assets/img/photography/birds.jpg"
     data-pswp-width="2048"
     data-pswp-height="1365">
    <img src="/assets/img/photography/birds.jpg" alt="pigeons walking across a city sidewalk" />
  </a>

  <a href="/assets/img/photography/jerseys.jpg"
     data-pswp-width="1365"
     data-pswp-height="2048">
    <img src="/assets/img/photography/jerseys.jpg" alt="nun walking down the street" />
  </a>

<a href="/assets/img/photography/ninetyninecents.jpg"
     data-pswp-width="2400"
     data-pswp-height="1600">
    <img src="/assets/img/photography/ninetyninecents.jpg" alt="brick building with grafitti" />
  </a>

<a href="/assets/img/photography/nun.jpg"
     data-pswp-width="3456"
     data-pswp-height="5184">
    <img src="/assets/img/photography/nun.jpg" alt="bicycle parked on a city street" />
  </a>

<a href="/assets/img/photography/singlemanwalking.jpg"
     data-pswp-width="3150"
     data-pswp-height="2100">
    <img src="/assets/img/photography/singlemanwalking.jpg" alt="man walking with his back turned" />
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

