<script>
	import {Details, Carousel} from '$lib';

    /** @type {import('./$types').PageData} */
    export let data;

    let showModal = true;
    const toggle = () =>{
		showModal = !showModal;
	}

	console.log(data.people[0]);

	let people = data.people;
	const person_id = 72;
	export let peep = person_id;
	
	
    // Check if the data has been received and is an array
    // console.log("Received data in +page.svelte:", data);
</script>

<!-- Only render if we have people in the data -->


{#if 10 > 2}
	<p>10 bigger</p>
	{#each people as person }
		{#if person.id === peep && person.name.length < 0 }
		<Details>
			<section>
				<p>mystery person</p>
			</section>
			
		</Details>
			
	
			
		{:else if person.id === peep && person.name.length > 0}
		<Details showModal={showModal} on:click={toggle}>

			<section>
				<article class="p_info">
					<ul>
						<li class="name">{person.name} {person.surname}</li>
						<li>squad_id :{person.squad_id}</li>
						<li>fun fact {person.bio}</li>
					</ul>
				</article>
				<article class="p_img">
					<!-- <h1>Details img</h1> -->
					<img src="{person.avatar}" alt="{person.name}-{person.squad_id}">

				</article>
				<article class="p_frame">
					<div>
						<!-- <p>iframe github or other</p> -->
						<a href={person.website}>
							<!-- website -->
							<iframe src={person.website}  frameborder="0"></iframe>
						</a>

					</div>
				</article>
			</section>
			<section>
				<div class="carousel">
					<Carousel people={data.people} {peep}  />
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




