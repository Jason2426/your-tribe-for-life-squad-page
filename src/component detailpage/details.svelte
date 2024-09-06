<script>
	// import { log } from 'degit/dist/index-688c5d50';
	// import { onMount } from 'svelte';
	export let data;

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
	.backdrop {
		display: grid;
		place-content: center;
		position: fixed;
		width: 100%;
		height: 100%;
		inset: 0;
		background-color: rgba(0, 255, 255, 0.611);
		backdrop-filter: blur(3px);
	}

	.modal{
		background-color: rgba(255, 255, 255, 0.633);
		/* outline: 1px solid ; */
		width: 48vw;
		height: 48vh;
		backdrop-filter: blur(3px);
		
		/* aspect-ratio:1/1; */
	}

	
</style>