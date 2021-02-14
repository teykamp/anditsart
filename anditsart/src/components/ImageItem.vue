<template>
    <div>        
        <img class="image" v-bind:src="image.address">
        <p class="title">{{image.title}}</p>
        <hr style="width:30%;text-align:center;background-color:#000;">
        <p class="author">by {{image.author}}</p>
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
    width: 460px;
    height: 460px;
    object-fit: contain;
}
.title {
    padding-top: 10px;
    padding-bottom: -10px;
    color: rgb(17, 17, 17);
    font-family: Georgia, 'Times New Roman', Times, serif;
}

.author {
    color: rgb(17, 17, 17);
    font-family: Georgia, 'Times New Roman', Times, serif;

}
</style>