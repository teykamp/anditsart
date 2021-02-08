<template>
    <div>
        <div class="test" v-bind:key="image.id" v-for="image in images">
            <b-col align-v="center" align-h="center">
                <ImageItem v-bind:image="image"/>
            </b-col>
        </div>
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
.test{
    background: #000;

}

</style>