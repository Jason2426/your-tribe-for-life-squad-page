<script>
	import Details from '../../component detailpage/details.svelte';

    /** @type {import('../$types').PageData} */
    export let data;
    let showModal = true;
    const toggle = () =>{
		showModal = !showModal;
	}
    // Check if the data has been received and is an array
    console.log(data);
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

{#if 10 > 2}
	<p>10 bigger</p>
	<Details showModal={showModal} on:click={toggle}>
		<section>
			<article>
				<ul>
					<li>name</li>
					<li>age</li>
					<li>fun fact</li>
				</ul>
			</article>
			<article>
				<h1>Details img</h1>
				<img src="./static/images/A19F6889-518F-406C-9590-2F7FD69AD278_4_5005_c.jpeg" alt="">

			</article>
			<article>
				<div>
					<p>iframe github or other</p>
					<iframe src="" frameborder="0"></iframe>
				</div>
			</article>
		</section>
	</Details>
{/if}

<button on:click={toggle} > open modal

</button>

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
  text-wrap: balance;
  /* container-type:inline-size; */

}

	section{
		position: relative;
		display: flex;
		/* background-color: #f0f0f0; */
		/* outline: solid; */
		height: 100%;
		padding: 2%;
		
	}
	article{
		outline:1px solid green;
		flex: 1;
		
		
	}
	article div{
		/* width: ; */
		height: 100%;
		/* background-color: bisque; */
	}

	iframe{
		width: 100%;
	}
</style>




