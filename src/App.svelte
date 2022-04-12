


<script>



    import Menu from './Menu.svelte';
    import ImageSlot from "./ImageSlot.svelte";

    let imgs1;
    let imgs2;
    let page = 'Home';

</script>


<Menu id="menu" bind:page={page} bind:imgs1={imgs1} bind:imgs2={imgs2}/>

<div class="wrap ">
    {#if page === 'Home'}
        <img style="width: 800px" class="mainImage"
             src="https://static.wixstatic.com/media/e23135_668bb694d4c84c618ffdf76b44c6c31b~mv2.jpg/v1/fill/w_980,h_948,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/e23135_668bb694d4c84c618ffdf76b44c6c31b~mv2.jpg" alt="mainimg">

    {:else}

        <ImageSlot classes="left" bind:list={imgs1}/>
        <ImageSlot classes="right" bind:list={imgs2}/>
        
    {/if}

</div>


<style>
    .mainImage {
        max-width: 100%;
        max-height: 100%;
        left: 0;
        right: 0;
        top: 0;
        bottom: 0;
        margin: auto;
        overflow: auto;
        position: fixed;
    }


    .wrap {
        max-width: 2000px;
    }

    .center {
        margin-left: auto;
        margin-right: auto;
    }


</style>