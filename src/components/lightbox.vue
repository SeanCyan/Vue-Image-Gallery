<template>
    <div class="lightbox">
        <font-awesome-icon icon="times-circle" size="3x" class="fa-times-circle" @click="this.$parent.hideLbx"></font-awesome-icon>
        <font-awesome-icon icon="angle-left" size="3x" class="fa-angle-left" @click="this.$parent.showPrev" />
        <font-awesome-icon icon="angle-right" size="3x" class="fa-angle-right" @click="this.$parent.showNext"/>
        <img class="lbxImg" :src=this.$parent.src>
    </div>
</template>

<script>

export default {
    name: 'Lightbox',   
}

</script>