<script>
	
	export let people;
</script>


{#each people as person}
	<!-- <Card /> -->
	<div>
		<p>{person.name}</p>
	</div>
{/each}

<style>

	p {
		color: red;
	}
</style>