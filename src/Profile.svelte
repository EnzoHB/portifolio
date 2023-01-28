<script>

    export let file;
    export let amount; 
    
    export let name = 'Enzo'
    export let followers = 326
    export let account = 'enzohosi';

    function random() {
        return Math.floor(Math.random() * 10 ** 3)
    };

    let images = [];

    for (let i = 0; i < amount; i++) {
        images.push(`./static/profiles/${file}/${i}.png`);
    };


</script>

<div class=container>
    <div class=info>
        <div class=icon>
            <img src='./static/profiles/{file}/profile.jpg' alt='Enzo'>
        </div>
        <div class=social>
            <div style='font-weight: 700'>{name} &centerdot {followers} seguidores</div>
            <div>@{account}</div>
        </div>
    </div>
    <div class=wrapper>
        <div class=media>
            {#each images as image} 
                <img alt="" width=500 height=500 src={image}>
            {/each}
        </div>
    </div>
</div>  

<style> 
    .container {
        box-sizing: border-box;

        padding-left: 20px;
        padding-right: 20px;

        width: 100%;
        gap: 30px;

        display: flex;
        flex-direction: column;
    }

    .icon {
        width: 100px;
        aspect-ratio: 1;
        
        background-color: transparent;
        border-radius: 50%;

        display: grid;
        place-items: center;
    }

    .icon > img {
        width: 100%;
        aspect-ratio: 1;
        background-size: cover;
    }

    .info {
        display: flex;
        gap: 20px;

        font-size: 1.5vw;
    }

    .social {
        height: 100%;
        display: flex;
        flex-direction: column;
    }

    img {
        border-radius: 10px;
    }

    .media {
        width: 100%;

        display: flex;
        gap: 20px;

        padding-bottom: 20px;

        overflow-y: hidden;
        overflow-x: scroll;
    }



    /* width */
    ::-webkit-scrollbar {
      height: 10px;
    }

    /* Track */
    ::-webkit-scrollbar-track {
      background: #f1f1f1;
    }

    /* Handle */
    ::-webkit-scrollbar-thumb {
      background: #888;
      width: 5px;
      border-radius: 20px;
    }

    /* Handle on hover */
    ::-webkit-scrollbar-thumb:hover {
      background: #555;
    }
</style>