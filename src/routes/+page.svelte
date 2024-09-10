<script>
	// import Topbar from '../lib/Topbar.svelte';
    import {Details, Carousel,Topbar} from '$lib';

    /** @type {import('./$types').PageData} */
    export let data;
   
    
    // Check if the data has been received and is an array
    // console.log("Received data in +page.svelte:", data);
</script>

<Topbar /> 

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
</style>