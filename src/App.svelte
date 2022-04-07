<script>
    import Nested from './Nested.svelte';
    import Menu from './Menu.svelte';

    let cats1 = [
        {
            id: 'J---aiyznGQ',
            name: 'https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_360,h_537,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%201x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_720,h_1074,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%202x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1080,h_1611,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%203x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1440,h_2148,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%204x,%20https://static.wixstatic.com/media/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.jpg/v1/fill/w_1717,h_2561,q_90/e23135_0c56e35d71dd4b2baf1c5ca96d0c4c52~mv2.webp%205x'
        },
        {
            id: 'J---aiyznGQ',
            name: 'https://static.wixstatic.com/media/e23135_7fc60156b51d4f2c95e590ed917b60e0~mv2.jpg/v1/fill/w_385,h_385,q_90/e23135_7fc60156b51d4f2c95e590ed917b60e0~mv2.webp'
        },
        {
            id: 'J---aiyznGQ',
            name: 'https://static.wixstatic.com/media/e23135_d0024c90b90e446a99ab232a6bc0e416~mv2.jpg/v1/fill/w_360,h_540,q_90/e23135_d0024c90b90e446a99ab232a6bc0e416~mv2.jpg'
        },
        {
            id: 'J---aiyznGQ',
            name: 'https://static.wixstatic.com/media/e23135_ca5ea0f739e34fa3b34c535a203f27f5~mv2.jpg/v1/fill/w_360,h_540,q_90/e23135_ca5ea0f739e34fa3b34c535a203f27f5~mv2.jpg'
        },

    ];

    let cats2 = [
        {
            id: 'J---aiyznGQ',
            name: 'https://static.wixstatic.com/media/e23135_13bd14f0d01d4ab49d796b19a4c4209c~mv2.jpg/v1/fill/w_640,h_794,q_90/e23135_13bd14f0d01d4ab49d796b19a4c4209c~mv2.webp'
        },
        {
            id: 'J---aiyznGQ',
            name: 'https://static.wixstatic.com/media/e23135_b0dc8f149cd6460ba12661189bcbe876~mv2.jpg/v1/fill/w_640,h_428,q_90/e23135_b0dc8f149cd6460ba12661189bcbe876~mv2.webp'
        },
        {
            id: 'J---aiyznGQ',
            name: 'https://static.wixstatic.com/media/e23135_25a25ae02e034ee198c4a4f3581b1c89~mv2.jpg/v1/fill/w_640,h_854,q_90/e23135_25a25ae02e034ee198c4a4f3581b1c89~mv2.webp'
        },
        {
            id: 'J---aiyznGQ',
            name: 'https://static.wixstatic.com/media/e23135_e57d9e3a42404d7c93bf6e300166c977~mv2.jpg/v1/fill/w_640,h_960,q_90/e23135_e57d9e3a42404d7c93bf6e300166c977~mv2.webp'
        },

    ];

</script>

<div class="navbar">
    <Menu id="menu"/>
</div>

<div class="contents center ">
    <div class="left">
        {#each cats1 as { id, name }, i}
            <img class="center" src={name}>
        {/each}
    </div>
    <div class="right">
        {#each cats2 as { id, name }, i}
            <img class="center" src={name}>
        {/each}
    </div>
</div>


<style>



img{
    width: 80%;
    height: auto;
    float: left;
    margin-bottom: 100px;
    position: relative;
}
.navbar{
    height: 60px;


}
.contents{
    max-width: 2000px;
}

.center{
    margin-left: auto;
    margin-right: auto;
}

.left{
    width: 50%;
    height: 100px;
    /*background-color: black;*/
    float: left;
}
.right{
    width: 50%;
    height: 100px;
    /*background-color: red;*/
    float: left;
}
</style>