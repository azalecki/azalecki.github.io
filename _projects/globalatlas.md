---
layout: page
title: Global Studies Atlas
description: My first gig 
img: assets/img/cropped/euro_crop.png
importance: 2
category: cartography
giscus_comments: true
---

My first gig as an undergraduate was working for Professor Guntram Herb on his Global Studies Atlas. When I joined the team, the atlas was just an idea with an outline. In the end it would take 3 years, 3 professors and __ cartographic assistants to get the atlas printed. This summer I had the pleasure of finally holding the completed work in my hands. 

What I really loved about this work is how collaborative it was. There were a couple of maps that feel distinctly "mine" because coincidently I ended up working on the design elements mostly myself. However, for the most part all of the final maps went through several revisions by several different people over the 3 years. 

For example, over a winter I with one of my peer, Grace Sokolow, drafted the layers and data in its beginning stages needed for a historical map of the cold war which was then passed onto another peer, Pete Strefurt where he added the finishing cartographic touches. 


<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/religion.png" title="Religious Affiliation Map" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/waterpollution.png" title="Water Pollution Map" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    These are just two examples of the types of maps that I made for the atlas.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:



{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
