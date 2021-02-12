
<template>
<!-- to start use "vue ui" -->
  <div id="app">

    <div>
      <!-- left aligned nav items -->
      <b-navbar toggleable="lg" type="dark" variant="dark">
        <b-navbar-brand href="#">anditsart</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="https://github.com/">Github</b-nav-item>
            <b-nav-item href="https://twitter.com/">Twitter</b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-form>
              <img class=searchIco src=https://images.vexels.com/media/users/3/132068/isolated/preview/f9bb81e576c1a361c61a8c08945b2c48-search-icon-by-vexels.png>
              <b-form-input size="sm" class="mr-sm-2" v-model="search" placeholder="Search"></b-form-input>
              <!-- <b-button size="sm" class="searchbtn" type="submit">Go!</b-button> -->
            </b-nav-form>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>

    <!-- end nav -->
    <!-- start images -->
    <b-container fluid classs="format">
      <ImageCards v-bind:images="filteredImg"/>
    </b-container>
    <button class="toTop" @click="scrollToTop()">
      <i class="arrow up">
      </i>
    </button>
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
      images: [], // imports from ./public/images.json
      search: ""
    }
  },
  computed: {
    filteredImg: function() {
      return this.images.filter((image) => {
        return image.author.match(this.search) || image.title.match(this.search);
      });
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
  border: none;
  padding: 10px;
  background: none;
}
.searchIco {
  width: 30px;
  height: 30px;
  margin-right: 20px;
}

</style>
