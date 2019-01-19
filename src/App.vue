<template>
  <div id="app" class="grid">
    <Gallery/>
  </div>
</template>

<script>

import Gallery from '@/components/gallery'

export default {
  name: 'App',
  components: {
    Gallery,
  }
}

</script>

<style>

@import url('https://fonts.googleapis.com/css?family=Libre+Baskerville');

html {
    background-color: rgb(255, 255, 255);
    font-family: 'Libre Baskerville', serif;
}

h1 {
    padding: 20px;
}

.gallery {
    box-sizing: border-box;
    max-width: 1300px;
    padding: 0 50px;
    margin: 0 auto;
    column-count: 1;
    column-gap: 0;
    font-size: 0px;
}

gallery img {
    width: 100%;
}

@media all and (min-width: 768px){

.gallery {
    column-count: 3;
    margin: 50px auto;
}

}

@media all and (min-width: 1200px){

.gallery {
    column-count: 4;
    margin: 50px auto;
}

}

.thumbnail {
    width: 100%;
    transition: 0.5s ease-out;
}

.thumbnail:hover {
    cursor: pointer;
    transform: scale(.95);
}

.lightbox {
    z-index: 10;
    position: fixed;
    top: 0; bottom: 0; left: 0; right: 0;
    background-color: rgba(0,0,0,.7);
    font-size: 16px;
}

.lbxImg {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
    max-height: 80vh;
    max-width: 60vw;
}

.fa-times-circle {
    position: absolute;
    top: 1%; right: 1%;
    color: white;
}

.fa-times-circle,
.fa-angle-left,
.fa-angle-right {
    cursor: pointer;
}

.fa-angle-left, .fa-angle-right {
    position: absolute;
    top: 50%;
    color: white;
}

.fa-angle-left {
    left: 5%;;
}

.fa-angle-right {
    right: 5%;
}

</style>

