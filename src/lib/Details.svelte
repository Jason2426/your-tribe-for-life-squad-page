<script>
	// import { log } from 'degit/dist/index-688c5d50';
	// import { onMount } from 'svelte';
	// export let data;
 	// import Carousel from "$lib/Carousel.svelte";
	// if(data.people){
	// 	console.log("data.people", data.people)
	// }

	export let showModal = false;
</script>


<!-- {#if data.people}
	<div class="details">
		<p>yup</p>
	</div>
	{:else}
	<p>no content</p>
	
{/if} -->
{#if showModal}
<div class="backdrop" on:click|self>

    <div class="modal">
		<!-- <p>modal++</p> -->
		<slot></slot>
	</div>



</div>
{/if}

<style>

*,
*::before,
*::after,
html {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  list-style: none;
  appearance: none;
  text-decoration: none;
  scroll-behavior: smooth;
  scrollbar-gutter: stable;
  scrollbar-width: thin;
  color: green;
}
	.backdrop {
		display: grid;
		place-content: center;
		position: fixed;
		inset: 0;
		background-color: rgba(152, 198, 198, 0.611);
		backdrop-filter: blur(3px);
	}

	.modal{
		/* background-color: white; */
		outline: 1px solid ;
		border-radius: 10px;
		width: 70vw;
		height: 60vh;
		/* color: red; */
	}

	.modal > :nth-child(1){
		outline: 1px solid;
	}
</style>