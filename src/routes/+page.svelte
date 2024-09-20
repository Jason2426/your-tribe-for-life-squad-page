<script>
	// Stylesheets
	import '../styles/grid.css';
  	import '../styles/random-card-component.css';
	import '../styles/deail.css';

	import '../styles/global.css';
	import '../styles/intro-section.css';
	import '../styles/meet-our-team.css'
	import '../styles/fonts.css';
	import '../styles/animation.css';

	// Components
	import CardComponent from "$lib/card-component.svelte";
	import Details from '$lib/Details.svelte';

	// Variables
	/** @type {import('./$types').PageData} */
	export let data;

	let people = data.people.map(peep => ({ ...peep }));
	
	
	export let selectedPerson = null;
	let isloaded = false;

	
	
	
// JS and functions
	const links = [
		{id:48,src:'/images/2D2A8708-B2FC-418D-967C-F21EC6D2E020_1_102_o.jpeg' },
		{id:16,src:'/images/2DECD1CC-399D-4A2F-B33A-EE4D3A77E553_4_5005_c.jpeg'},
		{id:8,src:'/images/3A2FC855-6E30-4443-8D61-B047C7F560B7_4_5005_c.jpeg'},
		{id:79,src:'/images/3C72843E-F6EA-4D56-8CF1-57B1908D6AF3_4_5005_c.jpeg'},
		{id:24,src:'/images/3DDFB72A-4A72-4CE3-8C0F-B49A706288A7_4_5005_c.jpeg'},
		{id:false,src:'/images/3F855E52-F25D-4F60-8E87-A19164C4AE69_4_5005_c.jpeg'},
		{id:75,src:'/images/4B7D6382-E2DD-4B8C-BACF-1CEF66F9A80F_4_5005_c.jpeg'},
		{id:44,src:'/images/5AFFC06D-5A19-42E3-8365-869AD6D12A29_4_5005_c.jpeg'},
		{id:81,src:'/images/6BED93D6-F18D-43B2-81E8-882FEB74D5F9_4_5005_c.jpeg'},
		{id:40,src:'/images/christopher.jpeg'},//christopher
		{id:55,src:'/images/39A2EE91-BCC8-4BC4-A7EE-E112140351ED_4_5005_c.jpeg'},
		{id:80,src:'/images/52BE9285-B979-4425-9788-D715D008B7CA_4_5005_c.jpeg'},
		{id:false,src:'/images/61DD70EC-D800-4785-A1BD-ACC9275B65C6_4_5005_c.jpeg'},
		{id:false,src:'/images/62BF8916-682D-460D-A5DD-A97E5678D070_4_5005_c.jpeg'},
		{id:false,src:'/images/075AE7C0-642D-4BFD-AF7D-44E479F9E164_4_5005_c.jpeg'},
		{id:23,src:'/images/80E05FF1-FEFC-4277-A533-35A23E0765D2_4_5005_c.jpeg'},
		{id:36,src:'/images/87DDE812-A203-49EE-A304-632056AF2DB5_4_5005_c.jpeg'},
		{id:54,src:'./images/tristan.jpeg'},// tristan
		{id:42,src:'./images/jason.jpeg'},// jason
		{id:41,src:'/images/434A4850-0F7C-4135-9FE3-CFA87BAF8E19_4_5005_c.jpeg'},
		{id:false,src:'/images/1532C412-5E9A-452E-AE18-D87CE16968A2_4_5005_c.jpeg'},
		{id:60,src:'/images/02748427-EF07-4CC5-AA4D-8B4D02140415_4_5005_c.jpeg'},
		{id:50,src:'/images/7905913E-722C-459A-BE02-2142E826F49A_4_5005_c.jpeg'},
		{id:73,src:'/images/63687383-4DED-4B21-B1D6-7A0B0049AC2B_4_5005_c.jpeg'},
		{id:82,src:'./images/daan.jpeg'},//daan
		{id:46,src:'/images/B5B98146-B819-43CB-9B77-C5C660A6E9DA_4_5005_c.jpeg'},
		{id:10,src:'/images/F78E4E64-3C6F-4B8B-AEAA-1D897BFD52D6_4_5005_c.jpeg'},
		{id:25,src:'/images/B40AD000-2775-4919-9527-674C6842ABBD_4_5005_c.jpeg'},
		{id:false,src:'/images/C94C0195-6A05-4F91-BD1F-AB8E22D2C5A9_4_5005_c.jpeg'},
		{id:32,src:'/images/CDA6B649-791F-43E7-965D-D51C226B4BB5_4_5005_c.jpeg'},
		{id:false,src:'/images/D3BD2AE8-4171-4855-B447-489ECCF39BD8_4_5005_c.jpeg'},
		{id:false,src:'/images/D5FC597F-C385-409A-9D19-D74BDABA1998_4_5005_c.jpeg'},
		{id:false,src:'/images/D5828D0D-7C52-498E-91E8-E68AA80EBEBE_4_5005_c.jpeg'},
		{id:26,src:'./images/annelinde.jpg',name:'annelinde'},//annelinde
		{id:85,src:'/images/D200900D-9E51-4D26-9125-C7993ED4A18D_4_5005_c.jpeg'},
		{id:14,src:'/images/DEE80F51-BF2E-424B-B792-B24F8A8527DE_1_102_o.jpeg'},
		{id:9,src:'/images/DF5516A1-5C9E-4390-B3E0-68F28CCB31C2_4_5005_c.jpeg'},
		{id:64,src:'./images/ellenoor.jpeg'},// ellenoor
		{id:false,src:'/images/F2FBA29C-B4A5-43A7-9618-69C70C6CC3AD_4_5005_c.jpeg'},
		{id:50,src:'/images/F7D4543D-945D-49F4-AE3B-FD77B8439ABD_4_5005_c.jpeg'},
		{id:29,src:false,name:'jesse'},
	];

		
	let localProfiles = links.map((link,index) =>({
		id: link.id,
		src: link.src,
		alt: `image ${index + 1}`,
		name: link.name,
	}))

	let imgArr = localProfiles.map(function(each){
		return each.src
	})




	// array combining function
	// Find the matching image by id
	// Combine the properties of the person and the image
	// let matched_pl = people.map(person => {
	// 	let matchingImage = images.find(image => image.id === person.id);

	// 	return {
	// 	...person,
	// 	...matchingImage
	// 	};
	// });

	// array combining function
	// Find the matching image by id
	// Combine the properties of the person and the image
	let matched_pl = localProfiles.map(profile => {
		let matchingImage = people.find(person => person.id === profile.id);

		return {
		...profile,
		...matchingImage
		};
	});

	export let chris  = matched_pl[9];
	// selectedPerson = chris

	function open(matched_pl){
		selectedPerson = matched_pl;
		console.log(selectedPerson);
	}

	function close(){
		selectedPerson = null;
		// console.log(selectedPerson);
	}

	function handleImagload() {
		isloaded = true;
	}

	function handleImagError() {
		console.log(isloaded);
		
	}

	
	
	
	
	
  
	// Functie om 5 willekeurige unieke links te kiezen
	function getRandomLinks(arr, count) {
		// Maak een lege array om de geselecteerde links in op te slaan
		const selectedLinks = [];

		// Blijf doorgaan totdat we het gewenste aantal links hebben
		while (selectedLinks.length < count) {
			// Kies een willekeurige index uit de array
			const randomIndex = Math.floor(Math.random() * arr.length);
			// Haal de link op die bij die willekeurige index hoort
			const selectedLink = arr[randomIndex];

			// Voeg de link toe aan de geselecteerde links als deze nog niet is toegevoegd
			if (!selectedLinks.includes(selectedLink)) {
				selectedLinks.push(selectedLink);
			}
		}
		// Geef de array met geselecteerde links terug
		return selectedLinks;
	}

	// Roep de functie aan om 5 willekeurige links te kiezen uit de 'links' array
	const imgSrcs = getRandomLinks(imgArr, 5);

	console.log(
	// `
	// Random img ${imgSrcs}
	// ----------------------
	// All the imags from link ${imgArr}`
	// matched_pl
	);

</script>

<main>
	<section class="intro-section">
		<div class="intro-text">
			<h1>Welcome to our Squadpage</h1>
			<p>
				We are a group of students passionate about front-end development, exploring ways to broaden
				our skills and deepen our understanding of webdesign.
			</p>
		</div>
		<section class="card-section-layout">
			{#each imgSrcs as imgSrc}
				<CardComponent 
				{imgSrc} 
				on:click={() => open(imgSrc)} 
				
				></CardComponent>
			{/each}
	</section>

	<!--Workspace Ellenoor-->
	<section class="meet-our-team">
		<div class="about-us">
			<!--H3-->
			<h3></h3>
			<p>Our team of frontend developers is a group of enthusiastic individuals focused on creating websites that are both user-friendly and visually appealing. We work well together to ensure everything runs smoothly, looks great, and is easy for users to understand.</p>
		</div>
		<section class="our-team-cards">
			<div class="card1 all-cards">
			</div>
			<div class="card2 all-cards">
			</div>
			<div class="card3 all-cards">
			</div>
			<div class="card4 all-cards">
			</div>
			<div class="card5 all-cards">
			</div>
			<div class="card6 all-cards">
			</div>
		</section>
	</section>
    
      <!--Workspace Tristan-->
	<section class="meet-our-tribe">
		<!--H3-->
		<div class="our-tribe-cards">

			<section class="masonry masonry--h">
				{#each matched_pl as p}
					{#if p == p}
						<figure class="masonry-brick masonry-brick--h" on:click={() => open(p)}>

							<img 
							src={p.src} 
							class="masonry-img" 
							alt="{p.name} {p.alt}"
							on:load={handleImagload}
							on:error={handleImagError}
							>
							<p>{p.name}</p>
						</figure>
					{:else}
						<figure class="masonry-brick masonry-brick--h" >
							<p>missing</p>
						</figure>
					{/if}
				{/each}
			</section>

			{#if selectedPerson}
				<div class="backdrop" on:click|self={close}>
					<Details
					sPerson = {selectedPerson}
					{close}
					>
				<p>{selectedPerson.id}</p>
				</Details>
				</div>
			{/if}
			
		</div>
	</section>
 </main>

