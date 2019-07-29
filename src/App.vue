<template>
  <div id="app">
    <Header  v-bind:msg="msg" />
    <Gallery v-bind:images="images"/>
    <div id="slider">
      <h1>{{msg}}</h1>
<!--       <div class="wall" v-if="images.length">
        <img class="image" v-bind:key v-for="(image) in images" v-bind:src="image.baseimageurl" />
      </div> -->
   
    </div>
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
      msg: 'Hello'
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
  padding: 0;
  color: #2c3e50;

}

.wall {
  display: flex;
  flex-wrap: wrap;
}

body, html {
  background-image: url("./assets/displaywall.jpeg" );
  height: 100%;
  background-repeat: no-repeat;
  background-size: cover;
}
.image {
  height: 300px;
  width: 200px;
}

</style>
