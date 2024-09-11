<script>
	import {Details, Carousel} from '$lib';

    /** @type {import('./$types').PageData} */
    export let data;

    let showModal = false;
    const toggle = () =>{
		showModal = !showModal;
	}
    // Check if the data has been received and is an array
    // console.log("Received data in +page.svelte:", data);
</script>

<!-- Only render if we have people in the data -->


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
				<img src="" alt="">

			</article>
			<article>
				<div>
					<p>iframe github or other</p>
					<iframe src="" frameborder="0"></iframe>
				</div>
			</article>
		</section>
	</Details>

	<Carousel people={data.people}/>
{/if}

<button on:click={toggle} > open modal

</button>






