<script>
	import {Details, Carousel} from '$lib';

	let setValue;
	export let person;
	export let people;
	export let showModal;
	export let toggle;
	export let person_id = 0 ;
	export let peep ;
	// export let setValue = () =>{
	// 	person_id = 40
	// }	
	function click (){
		// setValue();
		toggle();
		// console.log(setValue);
		peep = !peep && person.id;
		console.log(`person id ${person.id}`, `peep is ${peep}`);

	}
	
	
	// console.log(people[0]);


</script>

<li value={person.id}>
	
		<!-- <img src={person.avatar} alt="{person.name}" >	 -->
	
	
		<section on:click={click}>
			<h2>{person.name}</h2>
			<button  > open modal

			</button>
		</section>


		{#if person.id === peep && person.name.length < 0 }
		<Details>
			<section>
				<h1>mystery person</h1>
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
					<Carousel people={people} {peep}  />
				</div>
			</section>
		</Details>

		{/if}	
	
	


</li>

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
	
	
	
	
	
