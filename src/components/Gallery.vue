<template>
	<div>
		<h1>Gallery</h1>
		
		<div v-bind:key="image.id" v-if="images.length" v-for="image in images">
      <Piece v-bind:image="image" />
    </div>
	</div>
</template>

<script>
import Piece from './Piece.vue';

export default {
	name: "Gallery",
	components: {
		Piece
	},
	props: ["images"]
}
</script>

<style scoped>

</style>