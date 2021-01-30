<template>
    <div>
        <div v-bind:key="image.id" v-for="image in images">
            <img v-bind:src="image.address">
        </div>       
    </div>    
</template>

<script>
export default {
    name: "ImageCards",
    props: ["images"]
}
</script>

<style scoped>


</style>