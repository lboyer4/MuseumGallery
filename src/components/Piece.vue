<template>
	<div>
		<img v-bind:src="display.baseimageurl" />
	</div>
</template>

<script>
export default {
	name: "Piece",
	props: ["display"],

}

</script>

<style scoped>

	h1 {
		color: black;
	}

	img {
		height: 400px;
		margin: 20px;
		border: 5px solid #2c3e50;
		border-radius: 2px;
		
	}
	
</style>