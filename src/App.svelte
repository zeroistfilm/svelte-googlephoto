<script>


    import Menu from './Menu.svelte';
    import ImageSlot from "./ImageSlot.svelte";
    import {fade, fly} from 'svelte/transition';

    let imgs1;
    let imgs2;
    let page = 'Home';
    let windowWidth;

    let key;
    let keyCode;
    let index = 0;
    let imglist;
    let imgSrc = 'https://0dong.site/imgs/main.jpg';
    let visiable = true;
    // $: imgSrc = `https://0dong.site/imgs/cache/${imglist[index]}.jpg`

    $:{
        if (visiable === false) {
            setTimeout(() => {
                visiable = true;

            }, 500)
        }

    }

    fetch('https://0dong.site/imglist', {method: "GET"}).then(
        (res) => {
            res.json().then(
                (res) => {
                    imglist = res
                }
            )
        }
    );

    function handleClickPrev(e) {
        index -= 1;
        if (index < 0) {
            index = 0;
        } else if (index > imglist.length - 1) {
            index = imglist.length - 1
        }
        imgSrc = `https://0dong.site/imgs/cache/${imglist[index]}`
        visiable = false;

    }

    function handleClickNext(e) {
        index += 1;
        if (index < 0) {
            index = 0;
        } else if (index > imglist.length - 1) {
            index = imglist.length - 1
        }

        imgSrc = `https://0dong.site/imgs/cache/${imglist[index]}`
        visiable = false;

    }

    function handleKeydown(event) {
        key = event.key;
        keyCode = event.keyCode;
        if (key === 'ArrowRight' || key === 'ArrowDown') {
            index += 1;
            visiable = false;
        } else if (key === 'ArrowLeft' || key === 'ArrowUp') {
            index -= 1;
            visiable = false;
        }
        if (index < 0) {
            index = 0;
        } else if (index > imglist.length - 1) {
            index = imglist.length - 1
        }

        imgSrc = `https://0dong.site/imgs/cache/${imglist[index]}`


    }


</script>

<svelte:window bind:innerWidth={windowWidth} on:keydown={handleKeydown}/>

<!--<Menu id="menu" bind:page={page} bind:imgs1={imgs1} bind:imgs2={imgs2} bind:windowWidth={windowWidth}/>-->
<div class="navbar" style="text-align: center">
    <a class="" href="/">KimYoungDong</a>
</div>


<div class="wrap ">
    <!--{#if page === 'Home'}-->
    <div class='prev-zone' on:click={handleClickPrev}></div>
    <div class='next-zone' on:click={handleClickNext}></div>
    {#if visiable}
        <img class="mainImage" src={imgSrc} in:fly="{{ duration: 2000 }}" out:fade alt="mainimg">
    {/if}

    <!--{:else}-->

    <!--    <ImageSlot classes="left" bind:list={imgs1}/>-->
    <!--    <ImageSlot classes="right" bind:list={imgs2}/>-->

    <!--{/if}-->

</div>


<style>

    .navbar {
        height: 60px;
        width: 100%;
        margin:auto;
        position:center;
        foalt: right;
    }

    .prev-zone {
        width: 50% !important;
        height: 100% !important;
        max-height: 100% !important;
        max-width: 50% !important;
        position: relative !important;
        margin: auto !important;
        float: left !important;
        border: none !important;
        color: transparent !important;
        background: none !important;
        z-index: 999 !important;
    }

    .next-zone {
        width: 50% !important;
        height: 100% !important;
        max-height: 100% !important;
        max-width: 50% !important;
        position: relative !important;
        float: right !important;
        border: none !important;
        color: transparent !important;
        background: none !important;
        -webkit-touch-callout: none;
        -webkit-user-select: none;
        -khtml-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        -webkit-tap-highlight-color: transparent;
        z-index: 999 !important;
    }

    .mainImage {
        /*max-width: calc(80% - 100px);*/

        /*left: 0;*/
        /*right: 0;*/
        /*top: 0;*/
        /*bottom: 0;*/
        /*margin: auto;*/
        /*overflow: auto;*/
        /*position: fixed;*/
        /*transform: scale(1.1);*/
        /*transition: all 1s ease;*/


        width: auto !important;
        height: auto !important;
        max-height: 80% !important;
        max-width: 80% !important;
        position: absolute !important;
        top: 0 !important;
        bottom: 0 !important;
        left: 0 !important;
        right: 0 !important;
        margin: auto !important;
        border: 0px !important;
        z-index: 1 !important;
    }


    .wrap {

        margin: 0 auto !important;
        text-align: center !important;
        width: 100% !important;
        max-width: 100% !important;
        max-height: 100% !important;
        height: 100% !important;
        padding: 0px !important;

    }

    a {
        text-decoration: none;
        color: white;
        font-family: 'Arial', sans-serif;
        font-weight: bold;
        font-size: 12px;
        letter-spacing: 1px;
    }

    .center {
        margin-left: auto;
        margin-right: auto;
    }


</style>