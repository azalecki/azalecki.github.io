---
layout: page
title: Photography Now
description: 
img: assets/img/thumbnails/man_crop.jpg
importance: 2
category: other
---

<link rel="stylesheet" href="https://unpkg.com/photoswipe@5/dist/photoswipe.css">
<link rel="stylesheet" href="https://unpkg.com/photoswipe-dynamic-caption-plugin/photoswipe-dynamic-caption-plugin.css">


<style>
.pswp-gallery {
  column-count: 2;       /* always 2 columns */
  column-gap: 15px;
}
.pswp-gallery a {
  display: block;
  margin-bottom: 15px;
  break-inside: avoid;   /* keeps each image from splitting across columns */
}
.pswp-gallery a.wide {
  column-span: all;      /* landscape maps stretch across the full gallery width */
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


## Studio Portrait and Still Life Diptych

<div class="pswp-gallery">

  <a href="/assets/img/photography/portrait.jpg"
     data-pswp-width="2550" data-pswp-height="3300" data-cropped="true"
     target="_blank">
    <img src="/assets/img/photography/portrait.jpg" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

  <a href="/assets/img/photography/stilllife.jpg"
     data-pswp-width="1763" data-pswp-height="2576" data-cropped="true"
     target="_blank">
    <img src="/assets/img/photography/stilllife.jpg" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

</div>

## Time Series
<div class="pswp-gallery">

  <a href="/assets/img/photography/LongformLayout.png"
     data-pswp-width="4000" data-pswp-height="2546" data-cropped="true"
     target="_blank">
    <img src="/assets/img/photography/LongformLayout.png" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

</div>

## In the Style of
Create a photo series In the Style of a Photographer. Replicate one image by that photographer and then create 1 more image inspired by that photographer’s style.

In addition to the series, prepare a one minute presentation on the photographer, introducing their work, biographical information, and identifying major aspects of their technique and style. You will present this material before your critique.


<div class="pswp-gallery">

  <a href="/assets/img/photography/inthestyle1_57.jpg"
     data-pswp-width="2601" data-pswp-height="3642" data-cropped="true"
     target="_blank">
    <img src="/assets/img/photography/inthestyle1_57.jpg" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

  <a href="/assets/img/photography/inthestyle2_57.jpg"
     data-pswp-width="2601" data-pswp-height="3642" data-cropped="true"
     target="_blank">
    <img src="/assets/img/photography/inthestyle2_57.jpg" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>


</div>


## Final Project

<div class="pswp-gallery">

  <a href="/assets/img/photography/final_layout_medium.png"
     data-pswp-width="6630" data-pswp-height="6036" data-cropped="true"
     target="_blank">
    <img src="/assets/img/photography/final_layout_medium.png" alt="Description of image 4" />
    <span class="pswp-caption-content">
      <strong>Image 4 title</strong><br>Caption text here.
    </span>
  </a>

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
