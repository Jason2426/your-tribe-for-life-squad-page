<script>
	import {Cards} from '$lib';

    /** @type {import('./$types').PageData} */
    export let data;
	export let people = data.people;
	export let showModal = false;
    export const toggle = () =>{showModal = !showModal};
	export let setValue 
    // Check if the data has been received and is an array
    // console.log("Received data in +page.svelte:", data);
</script>

{#if people}
<h1>squad page</h1>
	{#each people as person }

		{#if 1 > 0}
		<Cards
			{showModal}
			{people}
			{person}
			{toggle}
			{setValue}
		></Cards>
		{/if}
			
		{/each}

	{:else}

	<h1>no data</h1>

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
}

	section{
		display: flex;
		gap: 3%;
		padding-top: 3%;
	}

	article{
		flex: 1;
		/* outline: solid; */
	}

	.p_info ul{
		margin-left: 9%;
	}

	.p_info li:nth-of-type(1){
		font-size: 200%;
	}
	

	img{
		width: 100%;
	}

	.p_frame{
		display: flex;
		flex-direction: column;
		justify-content:end;
	}

	.p_frame div{
		width: 100%;
		height: 100%;
		
	}

	.p_frame a{
		display: flex;
		aspect-ratio: 1/1;
		justify-content: flex-end;
		/* outline: solid red; */
		
		
		& iframe{
			position: relative;
			border-radius: 50%;
			width: 50%;
			aspect-ratio: 1/1;
			place-self: end;
			z-index: -1;
			/* outline: solid; */

		}

		& iframe::after{
			content: '';
			position: absolute;
			inset: 0;
			z-index: 2;
			color: aqua;
		}

	}

	.p_frame:has(:hover) iframe::after{
		content: 'website';
	}
	
	.carousel{
		width: 100%;
		height: min-content;
		overflow:scroll;
	}
</style>




