<template>
	<div class="long-strip">
	<div class="gallery">

		<button v-on:click="counter -= 1">Previous Image
    </button>
		<div class="art">
      <Piece v-bind:display="images[counter]" />
     </div>
    
    <button v-on:click="counter += 1">Next Image
    </button>
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
	data() {
    return {
      counter: 0,  
    }
  },
	props: ["images"]
}
</script>

<style scoped>

	.gallery {
		display: flex;
		margin-left: 20%;
	}

	.long-strip {
		padding: 20px;
		width: 100%;
		background-color: #E5E5E5;
		margin-top: 50px;
		text-align: center;
		height: 525px;
	}

	.art {
		height: 400px;
		width: 550px;
		align-content: center;
	}

	button {
		height: 50px;
		font-size: 20px;
		width: 160px;
		margin-top: 150px;
		border-radius: 5px;
	}

	button:hover {
		background-color: #32363B;
		color: #fff;
	}

</style>