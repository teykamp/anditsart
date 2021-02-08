<template>
    <div>
        <img v-bind:src="image.address" class="image" alt="Responsive image">
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
    border-radius: 50px;
    background: #fff;
}
</style>