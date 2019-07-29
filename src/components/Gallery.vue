<template>
	<div>
		<h1>Gallery</h1>
		<div class="wall" v-if="images.length">
      <img class="image" v-for="(image) in images" v-bind:key="image.id" v-bind:src="image.baseimageurl" />
    </div>
	</div>
</template>

<script>
export default {
	name: "Gallery",
	props: ["images"]
}
</script>

<style scoped>
</style>