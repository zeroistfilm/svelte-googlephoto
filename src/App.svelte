<script>
    import Nested from './Nested.svelte';
    import Menu from './Menu.svelte';

    let cats = [
        { id: 'J---aiyznGQ', name: 'https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_360,h_537,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%201x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_720,h_1074,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%202x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1080,h_1611,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%203x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1440,h_2148,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%204x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1717,h_2561,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%205x' },
        { id: 'J---aiyznGQ', name: 'https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_360,h_537,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%201x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_720,h_1074,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%202x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1080,h_1611,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%203x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1440,h_2148,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%204x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1717,h_2561,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%205x' },
        { id: 'J---aiyznGQ', name: 'https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_360,h_537,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%201x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_720,h_1074,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%202x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1080,h_1611,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%203x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1440,h_2148,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%204x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1717,h_2561,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%205x' },
        { id: 'J---aiyznGQ', name: 'https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_360,h_537,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%201x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_720,h_1074,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%202x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1080,h_1611,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%203x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1440,h_2148,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%204x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1717,h_2561,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%205x' },

    ];
</script>


<Menu id="menu"/>
<div style="display:flex">

    <div id="s-left">
        {#each cats as { id, name }, i}
            <img class="center flex-item" src={name}>
        {/each}
    </div>

    <div id="s-right">
        {#each cats as { id, name }, i}
            <img class="" src={name}>
        {/each}
    </div>

</div>


<style>
    #menu{
        float: left;
    }
    img{
        width: 100%;
        margin: 10%;
    }
#s-left{
    background-color: yellow;
    float: left;
    width: 200px;
    height: 700px;
}
#s-right{
    background-color: black;
    float: left;
    width: 200px;
    height: 700px;
}
</style>