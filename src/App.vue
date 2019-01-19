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

html {
    background-color: rgb(41, 41, 41);
}

.gallery {
    display: grid;
    grid-template-columns: 1fr;  
    grid-gap: 10px;
    justify-content: center;
    position: relative;
    width: 80%;
    flex: 1;
    margin: 50px auto;
    padding: 20px;
}

@media all and (min-width: 768px){
    .gallery {
            grid-template-columns: repeat(3, minmax(100px, 500px));  
            width: 60%;
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
}

.lbxImg {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
    width: 60%;
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

