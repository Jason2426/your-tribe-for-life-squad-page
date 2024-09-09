<script>
	
	export let people;
	export let peep
</script>

<h1>Im a carousel</h1>
<section>
	<div class="prev button">
		<button>prev btn</button>
	</div>
	<ul>
		{#each people as person}
		<!-- <Card /> -->
			{#if person.id === peep - 1}
				<li>
					<p>{person.name}</p>
					<p>{person.squad_id}</p>
				</li>
			{/if}
			{#if person.id === peep}
				<li>
					<p>{person.name}</p>
					<p>{person.squad_id}</p>
				</li>
			{/if}
			{#if person.id === peep + 1}
				<li>
					<p>{person.name}</p>
					<p>{person.squad_id}</p>
				</li>
			{/if}
			{#if person.id === peep + 2}
				<li>
					<p>{person.name}</p>
					<p>{person.squad_id}</p>
				</li>
			{/if}
		{/each}		
	</ul>
	<div class="next button">
		<button>next btn</button>
	</div>
</section>


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
		/* background-color: #f0f0f0; */
		width: 100%;
		height: 100%;
		padding-inline:3% ;
		display: flex;
		outline: solid;
	}

	ul{
		display: flex;
		justify-content: space-around;
		gap: 3%;
		width: 100%;
	}
	li{
		outline: 1px solid;
		width: 100%;
		align-content: center;
		background-color: #f0f0f0;
	}

	p {
		color: red;
	}
</style>