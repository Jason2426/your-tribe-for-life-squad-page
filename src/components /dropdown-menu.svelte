<script>
    let menuOpen = false;

    function toggleMenu() {
        menuOpen = !menuOpen;
    }
</script>

<button on:click={toggleMenu} class:open={menuOpen}>
    <svg width="44px" height="44px" viewBox="0 0 48 48">
        <g id="Layer_2" data-name="Layer 2">
          <g data-name="invisible box">
            <rect width="48" height="48" fill="none"/>
          </g>
          <g data-name="icons Q2">
            <g>
              <path class="line line1" d="M8 12h32"/>
              <path class="line line2" d="M8 24h32"/>
              <path class="line line3" d="M8 36h32"/>
            </g>
          </g>
        </g>
    </svg>
</button>

<nav class="dropdown-menu {menuOpen ? 'open' : ''}">
    <a href="/">Page 1</a>
    <a href="/">Page 2</a>
    <a href="/">Page 3</a>
</nav>

<style>
    button {
        background: inherit;
        border: none;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 0;
        margin: 0;
        z-index: 200;
    }
    svg {
        transition: transform 0.5s ease;
    }
    .line {
        stroke: #FFFFFF;
        stroke-width: 6;
        stroke-linecap: round;
        transition: transform 0.5s ease, opacity 0.5s ease;
    }
    .line1 {
        transform-origin: center;
        transform: rotate(0deg);
    }  
    .line2 {
        opacity: 1;
    }
    .line3 {
        transform-origin: center;
        transform: rotate(0deg);
    }
    .open .line1 {
        transform: rotate(45deg) translate(6px, 6px);
    }
    .open .line2 {
        opacity: 0;
    }
    .open .line3 {
        transform: rotate(-45deg) translate(6px, -6px);
    }
    .dropdown-menu {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 80vh;
        background-color: rgba(29, 16, 61, 0.9);
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        transform: translateY(-100%);
        transition: transform 0.65s ease;
        z-index: 150;
    }

    .dropdown-menu.open {
        transform: translateY(0);
    }

    .dropdown-menu a {
        font-family: 'Arial black', sans serif;
        color: white;
        text-decoration: none;
        font-size: 2em;
        margin: 15px 0;
        transition: color 0.3s ease;
    }

</style>