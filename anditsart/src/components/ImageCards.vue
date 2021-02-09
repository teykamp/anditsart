<template>
    <div>
        <b-row align-v="center" align-h="center">
        <div class="imcard" v-bind:key="image.id" v-for="image in images">
            <b-col align-v="center" align-h="center">
                <ImageItem v-bind:image="image"/>
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
    props: ["images"]
}
</script>

<style scoped>
.imcard{
    padding: 60px;
}

</style>