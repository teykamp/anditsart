<template>
    <div>        
        <img class="image" v-bind:src="image.address">
        <p>{{image.title}}</p>
    </div>
</template>

<script>
export default {
    name: "ImageItem",
    props: ["image"]
}
</script>

<style scoped>
.image {
    padding: 50px;
    background: #fff;
    width: 450px;
    height: 450px;
}
</style>