<script>

    export let page;
    export let imgs1;
    export let imgs2;

    async function LoadImage(value) {
        imgs1 = []
        imgs2 = []
        let size=1;
        console.log(value)
        let albumID;
        if(value==='Portrait'){
            albumID='AA7pFRVHCBMjiqCJTysvn4yXf9DysHNbVoYVOyF9WIko4VDYGqlQ-bE97FAeAS0bch9r3Pr_YxMz';
        }else if(value==='Place'){
            albumID='AA7pFRXZNRKZL-wzJxKAdQ1hinYz669SVctCr3TEr9DxDjkb0tBZ-dHO-5Ps2JLZVS0YQwSyfQDM';
        }else if(value==='Blue'){
            albumID='AA7pFRUp5qRMXwC-N5Fw18lVHq0V2rp9EieKYs9HZp_mmwWLJ0QGHN_spvVh7ju9W1tOqR5x12PD';
        }else if(value==='Green'){
            albumID='AA7pFRWGycpqN0cYjNMqiaiCgyabMxRtm0lbsQfca8MuVB71OnqynWOoHjOeDGsXfYbbRqzjF_d6';
        }else if(value==='Object'){
            albumID='AA7pFRVUmnmK67ggTYFYmPOM1xtzA1rQqEl0Bb8pJDFG8YdZMQtMQv9WGFJ12EoazGW0x5T7amaZ';
        }


        let res = await fetch(`http://127.0.0.1:8080/getImgWithAlbumID?AlbumID=${albumID}`, {mode:'cors'})
        let imglist = await res.json()
        imglist.photos.map((img, idx) => {
                if (idx % 2 !== 0) {
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
        <li><a href="http://localhost:8080/auth/google/callback">auth</a></li>
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