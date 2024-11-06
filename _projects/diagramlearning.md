---
layout: page
title: Diagrams for GIS Learning
description: 
img: assets/img/6.jpg
importance: 4
category: fun
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lightbox Gallery</title>

    <!-- Bootstrap CSS (make sure to include Bootstrap CSS) -->
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">

    <!-- Lightbox CSS -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/ekko-lightbox/5.0.0/ekko-lightbox.min.css" rel="stylesheet">

</head>
<body>

    <div class="container mt-5">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <!-- First Row of Images -->
                <div class="row">
                    <a href="assets/img/gisart/Azi_Tangent.png" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                        <img src="assets/img/gisart/Azi_Tangent.png" class="img-fluid">
                    </a>
                    <a href="assets/img/gisart/Cylin_Tangent.png" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                        <img src="assets/img/gisart/Cylin_Tangent.png" class="img-fluid">
                    </a>
                    <a href="assets/img/gisart/Con_Tangent.png" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                        <img src="assets/img/gisart/Con_Tangent.png" class="img-fluid">
                    </a>
                </div>

                <!-- Second Row of Images -->
                <div class="row mt-3">
                    <a href="assets/img/gisart/Azi_Secant.png" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                        <img src="assets/img/gisart/Azi_Secant.png" class="img-fluid">
                    </a>
                    <a href="assets/img/gisart/Cylin_Secant.png" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                        <img src="assets/img/gisart/Cylin_Secant.png" class="img-fluid">
                    </a>
                    <a href="assets/img/gisart/Con_Secant.png" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                        <img src="assets/img/gisart/Con_Secant.png" class="img-fluid">
                    </a>
                </div>

                <!-- Third Row of Images -->
                <div class="row">
                    <a href="assets/img/gisart/Cylin_Oblique.png" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                        <img src="assets/img/gisart/Cylin_Oblique.png" class="img-fluid">
                    </a>
                    <a href="assets/img/gisart/Cylin_Transverse.png" data-toggle="lightbox" data-gallery="example-gallery" class="col-sm-4">
                        <img src="assets/img/gisart/Cylin_Transverse.png" class="img-fluid">
                    </a>
                </div>
            </div>
        </div>
    </div>

    <!-- Bootstrap JS and dependencies (jQuery, Popper.js) -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.5.2/dist/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>

    <!-- Lightbox JS (Ekko Lightbox) -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ekko-lightbox/5.0.0/ekko-lightbox.min.js"></script>

    <script>
        // Initialize lightbox for images
        $(document).ready(function () {
            // Initialize Ekko Lightbox
            $(document).on('click', '[data-toggle="lightbox"]', function (event) {
                event.preventDefault();
                $(this).ekkoLightbox();
            });
        });
    </script>

</body>
</html>
