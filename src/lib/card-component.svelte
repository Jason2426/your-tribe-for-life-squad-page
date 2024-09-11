<script>
    export let imgSrc; // Ontvang de imgSrc prop
</script>

<style>
    figure {
        margin: 0;
        padding: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    img {
        position: absolute;
    }

    svg {
        width: 40em;
        height: 25em;
    }
</style>

<!-- Card Structure -->
<figure id="{imgSrc}">
    <img src={imgSrc} alt="squad member" height="300" width="200">
    
    <svg width="262" height="254" viewBox="0 0 262 254" fill="none" xmlns="http://www.w3.org/2000/svg">
        <g filter="url(#filter0_d_32_17)">
        <path d="M206.518 15.3952C229.016 20.1231 251.513 34.4697 256.729 54.1962C261.946 73.9228 249.719 99.1924 244.992 124.788C240.101 150.384 242.709 176.142 233.254 197.499C223.962 218.856 202.443 235.648 178.316 242.495C154.188 249.179 127.453 245.919 104.63 235.974C81.8065 225.866 63.0589 209.4 44.1483 190.978C25.2378 172.556 6.32719 152.34 4.2079 130.331C2.08861 108.322 16.5976 84.6827 28.3352 59.7392C40.0728 34.9588 48.713 8.87405 66.8084 2.02682C84.7409 -4.82042 112.129 7.56982 136.908 11.3195C161.687 15.2322 184.021 10.5044 206.518 15.3952Z" fill="url(#paint0_linear_32_17)"/>
        </g>
        <defs>
        <filter id="filter0_d_32_17" x="0" y="0" width="262" height="254" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
        <feFlood flood-opacity="0" result="BackgroundImageFix"/>
        <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/>
        <feOffset dy="4"/>
        <feGaussianBlur stdDeviation="2"/>
        <feComposite in2="hardAlpha" operator="out"/>
        <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.25 0"/>
        <feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_32_17"/>
        <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_32_17" result="shape"/>
        </filter>
        <linearGradient id="paint0_linear_32_17" x1="131" y1="0" x2="131" y2="246" gradientUnits="userSpaceOnUse">
        <stop stop-color="#BE84FF"/>
        <stop offset="1" stop-color="#724F99"/>
        </linearGradient>
        </defs>
    </svg>            
</figure>