<template>              
    <div class="content">
        <div class="gallery">
            <img v-for="img in gallery" :src=img.src @click="showLbx" class="thumbnail">
        </div>
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
                    src: "../../static/castelmezzano.jpg",
                },
                {
                    src: "../../static/nature.jpg",
                },
                {
                    src: "../../static/path.jpg",
                },
                {
                    src: "../../static/alberta.jpg",
                },
                {
                    src: "../../static/tree.jpg",
                },
                {
                    src: "../../static/flowers.jpg",
                },
                {
                    src: "../../static/tianjin.jpg",
                },
                {
                    src: "../../static/moraine.jpg",
                },
                {
                    src: "../../static/cloudss.jpg",
                },
                {
                    src: "../../static/finland.jpg",
                },
                {
                    src: "../../static/forest.jpg",
                },
                {
                    src: "../../static/yosemite.jpg",
                },
                {
                    src: "../../static/landscape.jpg",
                },
                {
                    src: "../../static/stanserhorn.jpg",
                },
                {
                    src: "../../static/woods.jpg",
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
        },  
        hideLbx: function() {
        this.isVisible = false;
        document.body.style.overflow = 'auto';
        },
        showNext: function() { 
        if (this.nextSrc.nextSibling === null) {
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