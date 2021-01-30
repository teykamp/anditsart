<template>
  <div id="app">

    <ImageCards/>

  </div>
</template>

<script>

// imports
import ImageCards from './components/ImageCards'

export default {
  name: 'App',
  components: {
  ImageCards
  },
  data() {
    return {
      art: [

      // put art objects here 

      ]
    }

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
