<template>
    <div>
        <p>{{image.title}}</p>
        <img v-bind:src="image.address">
    </div>
</template>

<script>
export default {
    name: "ImageItem",
    props: ["image"]
}
</script>

<style scoped>

</style>