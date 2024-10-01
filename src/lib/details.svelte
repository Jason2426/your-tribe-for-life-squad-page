<script>
	import '../styles/deail.css';
	export	let sPerson
	export	let close

	
	
</script>

<div class="modal" >

	<section>
		<article class="info">
			<ul>
				<h1>{sPerson.name} {sPerson.surname}</h1>
				<li> <span>{sPerson.bio}</span></li>
				<li><span>squad:</span> <span>{sPerson.squad_id}</span></li>
				<li> <span>{sPerson.role}</span></li>
				<!-- <li class="custom"><span>{sPerson.custom}</span></li> -->
			</ul>
		</article>
		<article class="profile">
			<div>
				<img src={sPerson.src} alt="{sPerson.alt}{sPerson.name}" >
			</div>
		</article>
		<article class="web-content">
			{#if sPerson.website}
			<iframe src={sPerson.website} frameborder="0"></iframe>
			<div>
				<a href={sPerson.website}>
					<span> <img src={sPerson.avatar} alt="websit{sPerson.name}"></span>
					<span><p>web link</p></span>
				</a>

			</div>

			{:else if sPerson.github_handle}

			<div class="nWeb">
				<a href={sPerson.github_handle}>
					<img src={sPerson.avatar} alt="{sPerson.name}">
					 <p>github link</p>
				</a>
				
	   		</div>

			{:else}
			
			<div class="nWeb">
					 <img src={sPerson.avatar} alt="{sPerson.name}">
			</div>
			{/if}
		</article>

		<article class="exit">
			<button on:click={close}>Terug</button>

		</article>
	</section>

	<slot></slot>
</div>

<style>


</style>