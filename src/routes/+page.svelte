<script>
    /** @type {import('./$types').PageData} */
    export let data;
    
    // Check if the data has been received and is an array
    console.log("Received data in +page.svelte:", data);

    import SquadLogo from '$lib/squad-logo.svelte';
    import DropdownMenu from '$lib/dropdown-menu.svelte';
    import CardComponent from "$lib/card-component.svelte";

    // import Topbar from '../lib/Topbar.svelte';
    import {Details, Carousel,Topbar} from '$lib';

  
    const imgSrcs = ['/images/Daan.png'];
    
</script>

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
    body {
		height: 100vh;
		width: 100vw;
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        background-position: 0px 0px;
        background-image: linear-gradient(180deg, #B285E5 10%, #660BCC 33%, #4C0899 58%, #000000 97%);
    }

    header {
        display: flex;
        justify-content: space-between;
        margin: 2.25em;
    }

    /* Media queries */

    @media (min-width: 40em){
        header {
            margin: 4.25em
        }
    }

    @media (min-width: 80em){
        header {
            margin: 5em
        }
    }


</style>

<body>
    <header>
        <SquadLogo />

        <!-- <ThemeSwitchBtn /> -->

        <DropdownMenu />
    </header>
    <main>
        <div>
            <!--Title-->
        </div>
        <div>
            <!--Main-cta-->
 {#each imgSrcs as imgSrc}
        <CardComponent imgSrc={imgSrc}></CardComponent>
    {/each}
        </div>
    </main>
</body>

