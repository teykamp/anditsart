
<template>
<!-- to start use "vue ui" -->
  <div id="app">
    <b-container fluid class="format">
      <b-row align-v="center" align-h="center">
          <ImageCards v-bind:images="images"/>
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
      this.fetchData();
  },
  methods: {
    async fetchData() {
      try {
        const res = await fetch("images.json");
        const val = await res.json();
        console.log(val);
        this.images = val;
      } catch {
        console.error("Cannot Fetch JSON Data");
      }
    }
  },
  data() {
    return {
      images: [] // imports from ./public/images.json
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
