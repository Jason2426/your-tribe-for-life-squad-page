<script>

     /** @type {import('./$types').PageData} */
     export let data;
     
     import Topbar from "$lib/Topbar.svelte";

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