<script>
    export let label = '';
    export let href = '';
    export let buttonStyle = 'main';

    function buttonStyles(){
        switch(buttonStyle){
        case "secondary":
            return "secondary";
        default:
            return "first";
    }
}
</script>

<a 
href={href}
class={`${buttonStyles()}`}
>
{label}
</a>

<style>
    a {
        font-family: 'Arial black', sans serif;
        font-size: 1.05em;
        text-decoration: none;
        padding: .75em 1.25em .75em 1.25em;
        border-radius: 2em;
        transition: ease-out 1.25s;
    }

    .first {
        background-color:#5F0CBC;
        border: 2px solid #B285E5;
        color: white;
    }

    .first:hover {
        /*hoverstyling*/
    }

    .secondary {
        /* other variants if needed */
        background-color: royalblue; /*test*/ 
    }
</style>