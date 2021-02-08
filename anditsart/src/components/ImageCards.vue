<template>
    <div>
        <div v-bind:key="image.id" v-for="image in images">
            <b-container fluid class="format">
                <b-row align-v="center">
                    <b-col>
                        <ImageItem v-bind:image="image"/>
                    </b-col>
                </b-row>
            </b-container>
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
    

</style>