<script>
	import Card from '$lib/Card.svelte';

	/** @type {import('./$types').PageData} */
	export let data;

	// Check if the data has been received and is an array
	console.log('Received data in +page.svelte:', data);
</script>

<nav>
	<a href="/">home</a>
	<a href="/squadpage">squadpage</a>
</nav>

<h1>home</h1>
<p>this is the home page.</p>

<!-- Only render if we have people in the data -->
{#if data.people}
	{#each data.people as person}
		<Card {person}></Card>
	{/each}
{:else}
	<!-- This will show if no people are available -->
	<p>No data available</p>
{/if}
