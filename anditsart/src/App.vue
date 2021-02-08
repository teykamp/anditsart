
<template>
<!-- to start use "vue ui" -->
  <div id="app">


    <b-container fluid class="format">
      <b-row align-v="center">
        <b-col>
          <ImageCards v-bind:images="images"/>
        </b-col>
      </b-row>
    </b-container>

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
  mounted(){
    try {
      this.fetchData();
    } catch {
      console.error("Cannot Fetch JSON Data");
    }
  },
  methods: {
    async fetchData(){
      const res = await fetch("images.json");
      const val = await res.json();
      console.log(val);
      this.images = val;
    }
  },
  data() {
    return {
      images: []
      // images: [ // put art objects here
      //   {id: 1, title: "google", address: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/12/Google_Photos_icon_%282020%29.svg/128px-Google_Photos_icon_%282020%29.svg.png"},
      //   {id: 2, title: "microsoft", address: "https://img-prod-cms-rt-microsoft-com.akamaized.net/cms/api/am/imageFileData/RE1Mu3b?ver=5c31"}, 
      //   {id: 3, title: "sensorbot", address: "http://sensorbot.org/img/sensorbot_logo_horiz_light.svg"}
      // ]
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
.format {
  background: #2c3e50;
}
</style>
