---
layout: page
title: Illustrating GIS Concepts
description: 
img: assets/img/thumbnails/balancedDesign_crop.png
importance: 1
category: other
---

Visuals are often the most effective way of communicating complex GIS concepts to students. 

I realized early on in my first teaching year just how important visuals are for effectively communicating complex GIS concepts to students. Now when holding office hours, I am invariably standing in front of a white board with a marker in hand. 

One of the smaller roles that I picked up while supporting GIS courses has been creating custom illustrations for our 

Sometimes the visuals we've needed for our course manual are proprieraty, low quality, or simply don't exist. In those cases, I've been asked to make them! 

Below you will find a selection of some of the diagrams, maps, etc. that I have produced for learning materials to be used in geog0261: Human Geography with GIS. Illustrations were created using QGIS, Adobe Illustrator, or a combination of both. Some of these illustrations live in our course manual while others in lab handouts, question sets, slides, exams*, etc. 


**Illustrations used for exams and other assessments I cannot freely distribute and are not included in this selection.*

<link rel="stylesheet" href="https://unpkg.com/photoswipe@5/dist/photoswipe.css">
<link rel="stylesheet" href="https://unpkg.com/photoswipe-dynamic-caption-plugin/photoswipe-dynamic-caption-plugin.css">

<style>
.pswp-gallery {
  column-width: 260px;   /* as many ~260px columns as fit: 3 on desktop, 2 on tablet, 1 on phone */
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
/* Make bold text in captions match the caption color */
.pswp-caption-content strong,
.pswp__dynamic-caption strong {
  color: inherit;
}
</style>

<div class="pswp-gallery" id="gallery--personal">

  <a href="/assets/img/gisart/figureground.png"
     data-pswp-width="2550"
     data-pswp-height="3626"
     target="_blank">
    <img src="/assets/img/gisart/figureground.png" alt="badFG" />
    <span class="pswp-caption-content">
      <strong>Bad Example of Figure Ground</strong><br>
      To demonstrate the difference between a map with good figure-ground contrast and one with poor figure ground-contrast, I developed these maps. The mapped elements are the same but one makes strategic style decisions to improve figure ground.<br> Students are asked to identify these stylistic choices and consider how it affects the visual hierarchy and legibility of the map. 
    </span>
  </a>

  <a href="/assets/img/gisart/projected_multi_panel.png"
     data-pswp-width="2400"
     data-pswp-height="1280"
     target="_blank">
    <img src="/assets/img/gisart/projected_multi_panel.png" alt="projected_multi_panel" />
    <span class="pswp-caption-content">
      <strong>Multi Panel Projection Layout</strong><br>
      A series of simple and cohesive map projection diagrams showing possible types of map surfaces. 
    </span>
  </a>

  <a href="/assets/img/gisart/Dev_Surf_Secant.png"
     data-pswp-width="2400"
     data-pswp-height="2400"
     target="_blank">
    <img src="/assets/img/gisart/Dev_Surf_Secant.png" alt="Dev_Surf_Secant" />
    <span class="pswp-caption-content">
      <strong>Developable Surface of a Secant Case</strong><br>
      A map projection diagram of the secant developable surface. This diagram is meant to be annotated by students to define where on the developable surface there will be the most/least distortion. 
    </span>
  </a>

  <a href="/assets/img/gisart/measureLat.png"
     data-pswp-width="2400"
     data-pswp-height="2400"
     target="_blank">
     <img src="/assets/img/gisart/measureLat.png" alt="measureLat" />
    <span class="pswp-caption-content">
      <strong>Measuring Latitude</strong><br>
      Diagram of an azimuthal equidistant projection centered on the North Pole. Used in lecture to demonstrate how to measure latitude. 
    </span>
  </a>

  <a href="/assets/img/gisart/measureLong.png"
     data-pswp-width="2400"
     data-pswp-height="2400"
     target="_blank">
    <img src="/assets/img/gisart/measureLong.png" alt="measureLong" />
    <span class="pswp-caption-content">
      <strong>Measuring Latitude</strong><br>
      Diagram of an orthographic map projection centered on the Equator and 73 degrees W. Used in lecture to demonstrate how to measure latitude. 
    </span>
  </a>

  <a href="/assets/img/gisart/overlays_all.png"
     data-pswp-width="2100"
     data-pswp-height="1500"
     target="_blank">
    <img src="/assets/img/gisart/overlays_all.png" alt="overlays_all" />
    <span class="pswp-caption-content">
      <strong>Overlay Scenarios</strong><br>
      A series of vector objects(points, lines, polygons) in varied locations. Used in a question set where students are asked to consider different outcomes of overlay tools and geometric predicates.
    </span>
  </a>

  <a href="/assets/img/gisart/maup.png"
     data-pswp-width="2550"
     data-pswp-height="1800"
     target="_blank">
    <img src="/assets/img/gisart/maup.png" alt="maup" />
    <span class="pswp-caption-content">
      <strong>Modifiable Areal Unit Problem (MAUP) Visual</strong><br>
    </span>
  </a>

  <a href="/assets/img/gisart/balancedDesign.png"
     data-pswp-width="3236"
     data-pswp-height="2490"
     target="_blank">
    <img src="/assets/img/gisart/balancedDesign.png" alt="balancedDesign" />
    <span class="pswp-caption-content">
      <strong>Quick Guide for Balanced Map Design</strong><br>
      A visual tool with tips for how to achieve balanced map design.
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
