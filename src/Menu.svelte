<script>

    export let page;
    export let imgs1;
    export let imgs2;

    async function LoadImage(value) {
        imgs1 = []
        imgs2 = []
        let size=1;
        console.log(value)
        let albumId;
        if(value==='Portrait'){
            albumId='AA7pFRWPEDn4rlMlaxSUHz7NLsEF9OFEKR7dL5TUNKpM7qzyQ9Ul68pXnOY7ahu8nbLx4piWBHtn';
        }else if(value==='Place'){
            albumId='AA7pFRW9DfUY4jNeX7Sl6q-6SqmHr3vwxo5R8cxhZpPnN9dbgfzZYFJhEq2wlON8KWxuNwzQOR_J';
        }else if(value==='Blue'){
            albumId='AA7pFRUVZhAfswul1RNq0cIa564fdR4G-_2rCQ5AkpBldI35LaqgOCgoXl9m9THOtgVn5bouj0E1';
        }else if(value==='Green'){
            albumId='AA7pFRX5NPYf_mp_jOcqFy2AHBq4uBwjNjgdqtKpmvwlL8gYH1WFu2jqWxSCzv5gNbRVEJBI5T0k';
        }else if(value==='Object'){
            albumId='AA7pFRUb4rB4bxdCfEpYETJk-3lZGj_S0H6hFxREl70EwyAS0ZHDWJUPiFM5-dXvlSTHZ9VLaBCC';
        }else if(value==='Wedding'){
            albumId='AA7pFRUEwEGXHLJvsy8TGLeyPiUpzFHNMaOt4vsPILrn5V8Pi7SKHhkOhAyc1iGvd6O_9KTr4syb';
        }


        let res = await fetch(`http://127.0.0.1:8080/getQueue/?albumId=${albumId}`, {mode:'cors'})
        let imglist = await res.json()
        imglist.photos.map((img, idx) => {
                if (idx % 2 === 0) {
                    imgs1 = [...imgs1, img]
                } else {
                    imgs2 = [...imgs2, img]
                }
            }
        )
    }
</script>

<div class="navbar">
    <ul id="menu">
        <li><a href="/" on:click|preventDefault={()=> {LoadImage('Home'); page='Home'}} >Home</a></li>
        <li><a href="/" on:click|preventDefault={()=> {LoadImage('Portrait');page='Portrait'}} >Portrait</a></li>
        <li><a href="/" on:click|preventDefault={()=> {LoadImage('Place');page='Place'}} >Place</a></li>
        <li><a href="/" on:click|preventDefault={()=> {LoadImage('Blue');page='Blue'}} >Blue</a></li>
        <li><a href="/" on:click|preventDefault={()=> {LoadImage('Green');page='Green'}} >Green</a></li>
        <li><a href="/" on:click|preventDefault={()=> {LoadImage('Object');page='Object'}} >Object</a></li>
        <li><a href="/" on:click|preventDefault={()=> {LoadImage('Wedding');page='Wedding'}} >Wedding</a></li>
        <li><a href="http://localhost:8080/album">auth</a></li>
    </ul>

</div>

<style>
    .navbar {
        height: 60px;
        width: 100%
    }

    ul {
        list-style-type: none;
        float: right;
    }
    a{
        text-decoration: none;
        color:white;
    }
    li {
        display: inline;
        margin-right: 40px;
        text-decoration: none;
    }

</style>