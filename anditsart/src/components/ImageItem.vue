<template>
    <div>        
        <img class="image" v-bind:src="image.address">
        <p class="title">{{image.title}}</p>
        <hr style="width:30%;text-align:center;background-color:#fff;">
        <p>by {{image.author}}</p>
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
    background: rgb(28, 31, 46);
    width: 460px;
    height: 460px;
}
.title {
    padding-top: 10px;
    padding-bottom: -10px;

}
</style>