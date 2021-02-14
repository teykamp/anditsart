
<template>
<!-- to start use "vue ui" -->
  <div id="app">

    <div>
      <!-- left aligned nav items -->
      <b-navbar toggleable="lg" type="dark">
        <!-- TODO CHANGE IMG -->
        <div class="logo">
          <Logo/>
        </div>
        <!-- <img class="logo" src="./assets/logo1.svg"> -->

        <b-navbar-brand><div class="anditsart">anditsart</div></b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="https://github.com/">Github</b-nav-item>
            <b-nav-item href="https://twitter.com/">Twitter</b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-form>
              <b-navbar-brand>
              <img class=searchIcon src=https://images.vexels.com/media/users/3/132068/isolated/preview/f9bb81e576c1a361c61a8c08945b2c48-search-icon-by-vexels.png>
            </b-navbar-brand>
              <b-form-input size="sm" class="mr-sm-2" v-model="search" placeholder="Search"></b-form-input>
              <!-- <b-button size="sm" class="searchbtn" type="submit">Go!</b-button> -->
            </b-nav-form>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>

    <!-- end nav -->
    <!-- start images -->
    <b-container fluid class="format">
      <ImageCards v-bind:images="filteredImg"/>
    </b-container>
    <!-- end images -->
    <div v-if="scrollTopUpdater">
      <button class="toTop" @click="scrollToTop()">
        <i class="arrow up"></i>
      </button>
    </div>

    <!-- bottom above footer -->
    <div v-if="noResultsUpdater">
      <p></p>
      <p  class="noResults">No Results Found!</p>
    </div>
    <!-- footer here -->
    <div class="footer">
      <Footer/>
    </div>
  </div>
</template>

<script>

// imports
import ImageCards from './components/ImageCards'
import Footer from './components/Footer'
import Logo from './components/Logo'

export default {
  name: 'App',
  components: {
    ImageCards,
    Footer,
    Logo
  },
  mounted() {
      this.fetchData();
  },
  methods: { // constant
    async fetchData() {
      // read json
      try {
        const res = await fetch("images.json");
        const val = await res.json();
        console.log(val);
        this.images = val; // NEVER UPDATES
      } catch {
        console.error("Cannot Fetch JSON Data");
      }
    },

    scrollToTop() {
      // scroll button
      window.scrollTo(0,0);
    }
  },
  data() {
    return {
      images: [], // imports from ./public/images.json
      // NEVER UPDATES!!!!!!!!!!!!! --> use filteredImg for dynamic image list
      search: ""
    }
  },
  computed: { // updates
    // search
    filteredImg: function() {
      return this.images.filter((image) => {
        return image.author.match(this.search) || image.title.match(this.search); // add to this for new parameters (very bad way but works)
      });
    },

    scrollTopUpdater: function() { // TODO: add passthrough of number to use for other v-if
      return this.filteredImg.length > 6;
    },

    noResultsUpdater: function() { // empty list?
      return this.filteredImg.length == 0; 
    }

  }
}
</script>

<style>

#app {
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #d7dde4;
  background: #0d1321; /* arrow bg */
  min-height: 600px;

}
.navbar{
  border-bottom: 1px solid #5f5fd3ff;
  background: rgba(0, 0, 0, 0.548);
}

.format {
  background: #0d1321
;
}
.arrow {
  border: solid rgb(255, 255, 255);
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 5px;
  height: 50px;
  width: 50px;
  box-shadow: black;

}
.up {
  transform: rotate(-135deg);
  -webkit-transform: rotate(-135deg);
}


.toTop {
  border: none;
  padding: 10px;
  background: none;
  transition-duration: 100ms;
}

.toTop:hover {
  transform: translateY(10px);
}

.searchIcon {
  width: 30px;
  height: 30px;
  transition-duration: 200ms;
  
}
.searchIcon:hover {
  transform: scale(1.5);
}

.anditsart {
  transition-duration: 200ms;
}
.anditsart:hover {
  color: #5f5fd3ff;

}

.logo {
  margin-right: 50px;
  transform: translateY(-15px);
}
.noResults {
  font-style: oblique;
  letter-spacing: 2px;
  padding-top: 20px;
  padding-bottom: 600px;
}
</style>
