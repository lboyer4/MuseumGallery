<template>
  <div id="app">
    <Header />
    <Gallery v-bind:images="images"/>
  </div>
</template>

<script>

import apikey from './assets/apikey.js';
import Header from './components/Header.vue';
import Gallery from './components/Gallery.vue';

export default {
  name: 'app',
  components: {
    Header,
    Gallery
  },
  data() {
    return {
      images: [],
    }
  },
  mounted: function() {
    this.getImages()
  },
  methods: {
    getImages: function() {
      const url = `https://api.harvardartmuseums.org/image?apikey=${apikey}`
      fetch(url)
      .then(response => response.json())
      .then(result => this.images = result.records)
    }}

}
</script>

<style>
* {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  box-sizing: border-box;
  margin: 0;
  color: #2c3e50;

}


body, html {
  background-image: url("./assets/blankwall.jpg" );
  height: 100%;
  background-repeat: repeat;
  background-size: contain;
  padding: 5px;
}


</style>
