
<template>
<!-- to start use "vue ui" -->
  <div id="app">
    <b-container fluid classs="format">
      <ImageCards v-bind:images="images"/>
    </b-container>
    <button class="toTop" @click="scrollToTop()"><i class="arrow up"></i></button>
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
    },

    scrollToTop() {
      window.scrollTo(0,0);
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
.arrow {
  border: solid rgb(255, 255, 255);
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 5px;
  height: 50px;
  width: 50px;
}
.up {
  transform: rotate(-135deg);
  -webkit-transform: rotate(-135deg);
}
.toTop {
  background: none;
  border: none;
  padding: 10px;
}

</style>
