<template>         
    <div class="gallery">
        <img v-for="img in gallery" :src=img.src class="thumbnail" @click="showLbx">
        <Lightbox v-show="isVisible"/>
    </div>
</template> 

<script>

import Lightbox from '@/components/lightbox'

export default {
    name: 'Gallery',
    components: {
        Lightbox,
    },
    data() {
        return {
            isVisible: false,
            src: "",
            nextSrc: "",
            prevSrc: "",
            currentSrc: "",
            gallery: [
                {
                    src: "static/flamingo.jpg",
                },
                {
                    src: "static/tree.jpg",
                },
                {
                    src: "static/flowers.jpg",
                },
                {
                    src: "static/tram.jpg",
                },
                {
                    src: "static/tianjin.jpg",
                },
                {
                    src: "static/lichterkette.jpg",
                },
                {
                    src: "static/snowy.jpg",
                },
                {
                    src: "static/finland.jpg",
                },
                {
                    src: "static/candy.jpg",
                },
                {
                    src: "static/stanserhorn.jpg",
                },
                {
                    src: "static/stones.jpg",
                },
                {
                    src: "static/mallow.jpg",
                },
                {
                    src: "/static/pumpkin.jpg",
                },
                {
                    src: "/static/woods.jpg",
                },
                {
                    src: "/static/maple.jpg",
                },
                {
                    src: "/static/nature.jpg",
                },
                {
                    src: "/static/balloon.jpg",
                },
                {
                    src: "/static/yosemite.jpg",
                },
                {
                    src: "/static/path.jpg",
                },
                {
                    src: "/static/northernlights.jpg",
                },
                ]
        }
    },
    methods: {
        showLbx: function(e) {
        this.isVisible = true;
        this.src = e.target.src;
        this.nextSrc = e.target;
        this.prevSrc = e.target;
        document.body.style.overflow = 'hidden';
        console.log(e.target);
        },  
        hideLbx: function() {
        this.isVisible = false;
        document.body.style.overflow = 'auto';
        },
        showNext: function() { 
        if (this.nextSrc.nextSibling === null || this.nextSrc.nextSibling.tagName !== 'IMG') {
            return
        } else {
            this.src = this.nextSrc.nextSibling.src;
            this.nextSrc = this.nextSrc.nextSibling;
            this.prevSrc = this.nextSrc; // ensures next/prev remain focused on the same gallery object
          }
        },
        showPrev: function() {
        if (this.prevSrc.previousSibling === null) {
            return
        } else {
            this.src = this.prevSrc.previousSibling.src;
            this.prevSrc = this.prevSrc.previousSibling;
            this.nextSrc = this.prevSrc; // ensures next/prev remain focused on the same gallery object
          }
        }
},
}
</script>