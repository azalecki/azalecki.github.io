---
layout: page
title: Making a Medieval City
img: assets/img/thumbnails/forestpreserve_crop.png
importance: 6
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

<div class="pswp-gallery">

  <a href="/assets/img/medieval/reiherswald_plan.png"
     class="wide" 
     data-pswp-width="3294" data-pswp-height="2480" data-cropped="true"
     target="_blank">
    <img src="/assets/img/medieval/reiherswald_plan.pn" alt="Description of image 4" />
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


