<template>
  <div id="app">
    <div v-if="images.length">
      <img v-for="(image) in images" v-bind:src="image.baseimageurl" />
    </div>
  </div>
</template>

<script>

import apikey from './assets/apikey.js'
export default {
  name: 'app',
  data: function() {
    return {images: []}
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
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
