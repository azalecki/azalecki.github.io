---
layout: page
title: Personal Projects
description: Here you will find projects that I have made because I wanted to make them (not because someone else wanted me to make them).
img: assets/img/thumbnails/forestpreserve_crop.png
importance: 6
category: cartography
---

<link rel="stylesheet" href="https://unpkg.com/photoswipe@5/dist/photoswipe.css">

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
</style>

<div class="pswp-gallery" id="gallery--personal">

  <a href="/assets/img/forestpreserves/ForestPreservesoftheFarNorthwestSide2.png"
     data-pswp-width="761"
     data-pswp-height="2576"
     target="_blank">
    <img src="/assets/img/forestpreserves/ForestPreservesoftheFarNorthwestSide_shrunk2.jpg" alt="Map of the forest preserves of the Far Northwest Side, Chicago" />
  </a>

  <a href="/assets/img/burlington/novacancies_large.jpg"
     data-pswp-width="3000"
     data-pswp-height="4305"
     data-download-url="/assets/img/burlington/novacancies.png"
     target="_blank">
    <img src="/assets/img/burlington/novacancies_shrunk.jpg" alt="Map: Sorry, No Vacancies, a geography of Burlington's housing crisis" />
  </a>

  <a href="/assets/img/vturbanforms/vturbanforms_large.jpg"
     data-pswp-width="3000"
     data-pswp-height="5000"
     data-download-url="/assets/img/vturbanforms/vturbanforms.png"
     target="_blank">
    <img src="/assets/img/vturbanforms/vturbanforms_shrunk.jpg" alt="Map: The Various Urban Forms of Vermont, figure grounds of twelve Vermont towns" />
  </a>

</div>

<script type="module">
  import PhotoSwipeLightbox from 'https://unpkg.com/photoswipe@5/dist/photoswipe-lightbox.esm.min.js';
  import PhotoSwipe from 'https://unpkg.com/photoswipe@5/dist/photoswipe.esm.min.js';

  const lightbox = new PhotoSwipeLightbox({
    gallery: '#gallery--personal',
    children: 'a',
    pswpModule: PhotoSwipe
  });

  // Download button: saves the full-res file named in data-download-url
  lightbox.on('uiRegister', function () {
    lightbox.pswp.ui.registerElement({
      name: 'download-full',
      order: 8,
      isButton: true,
      tagName: 'a',
      html: {
        isCustomSVG: true,
        inner: '<path d="M20.5 14.3 17.1 18V10h-2.2v7.9l-3.4-3.6L10 16l6 6.1 6-6.1ZM23 23H9v2h14Z" id="pswp__icn-download"/>',
        outlineID: 'pswp__icn-download'
      },
      onInit: (el, pswp) => {
        el.setAttribute('download', '');
        el.setAttribute('target', '_blank');
        el.setAttribute('rel', 'noopener');
        pswp.on('change', () => {
          const url = pswp.currSlide.data.element?.dataset.downloadUrl;
          el.href = url || pswp.currSlide.data.src;
        });
      }
    });
  });

  lightbox.init();
</script>
