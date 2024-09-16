<script>
	/** @type {import('./$types').PageData} */
	export let data;

	// Check if the data has been received and is an array
	console.log('Received data in +page.svelte:', data);

	// import cards from '$lib/components/cards/cards.svelte';
</script>

<body>
	<nav>
		<a href="/">Home</a>
		<a href="/squadpage">Squadpage</a>
	</nav>

	<h1>squadpage</h1>
	<p>this is the squadpage page.</p>

	<!-- Only render if we have people in the data -->
	{#if data.people}
		<section>
			{#each data.people as person}
				<div class="person-card">
					<svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg" class="background-svg">
						<path
							fill="#5F0CBC"
							d="M33,-52.8C44.9,-43.7,58,-38.1,61.1,-28.7C64.2,-19.3,57.2,-6,56.7,9.2C56.1,24.4,62,41.6,57.7,54.4C53.4,67.1,39,75.5,23.9,78.9C8.7,82.3,-7.3,80.8,-19.3,73.6C-31.3,66.5,-39.3,53.7,-49.3,42.5C-59.3,31.3,-71.3,21.7,-72.8,10.5C-74.3,-0.6,-65.3,-13.1,-60.4,-29.1C-55.4,-45.1,-54.6,-64.4,-45.3,-74.7C-35.9,-84.9,-18,-86.1,-3.7,-80.3C10.6,-74.6,21.1,-62,33,-52.8Z"
							transform="translate(100 100)"
						/>
					</svg>
					<div class="person-info">
						<h2>{person.name}</h2>
						<p class="person-bio">{person.bio}</p>
					</div>
				</div>
			{/each}
		</section>
	{:else}
		<!-- This will show if no people are available -->
		<p>No data available</p>
	{/if}
</body>

<style>
	* {
		font-family: Arial, sans-serif;
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}

	body {
		z-index: -1;
		position: absolute;
		background-color: rgb(69, 67, 67);
		width: 100%;
	}

	nav {
		margin: 30px;
	}

	h1 {
		display: flex;
		place-content: center;
		align-items: center;
	}

	section {
		display: flex;
		flex-flow: column wrap;
		justify-content: center;
		align-items: center;
	}

	.person-card {
		position: relative;
	}

	.background-svg {
		position: absolute;
		top: 0;
		left: 0;
		z-index: -1;
		width: 100%;
		height: 100%;
	}

	.person-info {
		position: relative;
		z-index: 1;
		padding: 20px;
		height: 300px;
		flex: 1 1 160px;
	}

	h2 {
		color: rgb(204, 199, 199);
		margin: 0;
		justify-content: center;
		align-items: center;
		display: flex;
		margin-top: 40%;
	}

	.person-bio {
		margin: 0;
		justify-content: center;
		align-items: center;
		display: flex;
	}
</style>
