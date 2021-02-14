<template>
    <div>
        <b-row align-v="center" align-h="center">
        <div class="imcard" v-bind:key="image.id" v-for="image in images">
            <b-col align-v="center" align-h="center">
                <button class="imgbutton" @click="openImage(image.address)">
                <ImageItem v-bind:image="image"/>
                </button>
            </b-col>
        </div>
        </b-row>
    </div>    
</template>

<script>

import ImageItem from './ImageItem.vue'

export default {
    name: "ImageCards",
    components: {
        ImageItem
    },
    props: ["images"],
    methods: {
        openImage: function(address) {   
            window.open(address, "_blank");    
      }
    }
}
</script>

<style scoped>
.imcard{
    padding: 60px;
}
.imgbutton {
    padding: 0;
    bottom: 50px;
    border: none;
    color: rgba(8, 8, 8, 0);
}

</style>