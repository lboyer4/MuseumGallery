<template>
	<div>
		<h1></h1>
		<img v-bind:src="image.baseimageurl"  />
<!-- 		<div class="wall" v-if="images.length">
      <img class="image" v-for="(image) in images" v-bind:key="image.id" v-bind:src="image.baseimageurl" />
    </div> -->
	</div>
</template>

<script>
export default {
	name: "Piece",
	props: ["image"]
}

</script>

<style scoped>
	h1 {
		color: black;
	}
</style>