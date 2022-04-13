<script>
    export var list;
    export var classes;
    let max_width=1000;
</script>

<div class={classes}>
    {#each list as {id, baseUrl}, i}
        <img src={baseUrl}>
    {/each}
</div>

<style>
    img {
        width: 80%;
        height: auto;
        float: left;
        margin-bottom: 20%;
        margin-left: 10%;
        position: relative;

        transition: all 1s ease;
    }
    img:hover {
        transition: all 2s ease;
        transform: scale(1.1); /* (150% zoom - Note: if the zoom is too large, it will go outside of the viewport) */
    }


    .left {
        width: 50%;

        /*background-color: black;*/
        float: left;
    }

    .right {
        width: 50%;

        /*background-color: red;*/
        float: left;
    }
</style>
