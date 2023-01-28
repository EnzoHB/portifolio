<script>
	import { onMount } from "svelte";
    import Profile from "./Profile.svelte";

    onMount(() => window.onload = () => {
        document.title = 'Portifolio';
        document.querySelector('#favicon').href = '/thumbnail_filled.png';
    })

    // --------- Header --------------- //  

    let header;
    let sticky;

    onMount(() => window.onscroll = () => {
        
        if (window.pageYOffset > header.offsetTop)
            return sticky = 'sticky';
            return sticky = '';

    });
</script>

<div class=container>
    <div bind:this={header} class=header class:sticky>
        <h1>Portifolio</h1>
    </div>
    <div class=profiles>
        <Profile file=forma amount=49 name='Forma Academia Fitness' account=formaacademiabady followers=1344/>
        <Profile file=vida-leve amount=9 name='Vida Leve' account=vidalevefranquia followers='14.8 mil'/>
        <Profile file=informatica amount=31 name='Universo Informatica' account=universoinformaticarp followers=2200/>
        <Profile file=criativa amount=49 name='Papelaria Criativa' account=papelariacriativa_rioptero followers=5106/>        
    </div>
</div>

<style>
    .header {
        background-color: rgb(255, 252, 247);
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);

        width: 100%;
        height: 10vh;

        display: grid;
        place-items: center;

        margin-bottom: 5vh;

        font-size: 1vw;
    }

    .profiles {
        display: flex;
        flex-direction: column;
        gap: 50px;

        overflow: hidden;
    }

    .container {
        margin-bottom: 30px;
    }
    
    .sticky {
        position: fixed;
    }

    /* Select the .profiles element immediately positioned after the .sticky element */
    .sticky + .profiles {
        padding-top: 15vh;
    }

</style>

