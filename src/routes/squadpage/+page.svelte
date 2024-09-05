<nav>
	<a href="/">Home</a>
	<a href="/squadpage">Squadpage</a>
</nav>

<h1>squadpage</h1>
<p>this is the squadpage page.</p>

<script>
    /** @type {import('./$types').PageData} */ 
    export let data;
    
    // Check if the data has been received and is an array
    console.log("Received data in +page.svelte:", data);
</script>

<!-- Only render if we have people in the data -->
{#if data.people}
    {#each data.people as person}
        <h1>{person.name}</h1>
        <p>{person.bio}</p>
    {/each}
{:else}
    <!-- This will show if no people are available -->
    <p>No data available</p>
{/if}