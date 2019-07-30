<template>
	<div>
		<h1></h1>
		<img v-bind:src="image.baseimageurl"  />
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

	img {
		height: 200px;
		margin: 20px;
		margin-left: 60px;
	}
	
</style>