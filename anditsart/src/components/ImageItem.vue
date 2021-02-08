<template>
    <div>
        <img v-bind:src="image.address" class="img-fluid" alt="Responsive image">
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

</style>