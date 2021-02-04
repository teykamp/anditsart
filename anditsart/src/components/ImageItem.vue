<template>
    <div>
        <p>{{image.id}}</p>
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