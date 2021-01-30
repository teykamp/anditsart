<template>
  <div id="app">

    <ImageCards v-bind:images="images"/>

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
      images: [ // put art objects here
        {id: 1, address: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/12/Google_Photos_icon_%282020%29.svg/128px-Google_Photos_icon_%282020%29.svg.png"},
        {id: 2, address: "https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RE1Mu3b?ver=5c31"}, 
        {id: 3, address: "http://sensorbot.org/img/sensorbot_logo_horiz_light.svg"}
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
  color: #d7dde4;
  margin-top: 60px;
  background: #2c3e50;
}
</style>
