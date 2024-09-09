<script>
	import { log } from 'degit/dist/index-688c5d50';
	import { onMount } from 'svelte';
	export let data;

	if(data.people){
		console.log("data.people", data.people)
	}
</script>




{#if data.people}
	<div class="details">


	</div>
	console.log(Data.people)
	{:else}
	<p>no content</p>
	console.log("no")

{/if}

