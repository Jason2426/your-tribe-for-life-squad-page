<script>
	import {Details, Carousel} from '$lib';

    /** @type {import('./$types').PageData} */
    export let data;

    let showModal = true;
    const toggle = () =>{
		showModal = !showModal;
	}

	console.log(data.people[0].id === 29);

	let people = data.people;
	
	
    // Check if the data has been received and is an array
    // console.log("Received data in +page.svelte:", data);
</script>

<!-- Only render if we have people in the data -->


{#if 10 > 2}
	<p>10 bigger</p>
	{#each people as person }
		
		{#if person.id === 44}
		<Details showModal={showModal} on:click={toggle}>

			<section>
				<article>
					<ul>
						<li>name : {person.name}</li>
						<li>squad_id :{person.squad_id}</li>
						<li>fun fact {person.bio}</li>
					</ul>
				</article>
				<article>
					<h1>Details img</h1>
					<img src="{person.avatar}" alt="{person.name}-{person.squad_id}">

				</article>
				<article>
					<div>
						<p>iframe github or other</p>
						<iframe src={person.website}  frameborder="0"></iframe>
						<a href={person.website}>website</a>

					</div>
				</article>
			</section>
			<section>
				<div class="carousel">
					<Carousel people={data.people} peep={person.id} />
				</div>
			</section>
		</Details>

		{/if}	
	{/each}
	
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
  scrollbar-gutter: stable;
  scrollbar-width: thin;
}

	section{
		display: flex;
	}

	article{
		flex: 1;
	}
	img{
		width: 100%;
	}

	iframe{
		width: 100%;
	}
	
	.carousel{
		width: 100%;
		height: min-content;
		overflow:scroll;
	}
</style>




