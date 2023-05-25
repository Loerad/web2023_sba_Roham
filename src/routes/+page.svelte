<script>
    import { onMount } from "svelte";

const BASE_URL = "https://rickandmortyapi.com/api";
let d;
let people;
let count = 6;
let peopleName;
onMount(async () => {
        const f = await fetch(`${BASE_URL}/character/`);
        d = await f.json();
        console.log(d);
        people = d
    })
</script>


<div class="grid">
    <div class="card">
        <img class="image" src={people?.results[0]?.image} />
        <div class="info">
            <h1 class="name">{people?.results[0]?.name}</h1>
            <h3 class="status"><div class="alive"></div>{people?.results[0]?.status}</h3>

            <h3 class="locationLabel">Last known location</h3>
            <h3 class="location"><a href="/location">{people?.results[0]?.location?.name}</a></h3>
        </div>
    </div>

    <div class="card">
        <img class="image" src={people?.results[4]?.image} />
        <div class="info">
            <h1 class="name">{people?.results[4]?.name}</h1>
            <h3 class="status"><div class="alive"></div>{people?.results[4]?.status}</h3>

            <h3 class="locationLabel">Last known location</h3>
            <h3 class="location"><a href="/location">{people?.results[4]?.location?.name}</a></h3>
        </div>
    </div>

    <div class="card">
        <img class="image" src={people?.results[7]?.image} />
        <div class="info">
            <h1 class="name">{people?.results[7]?.name}</h1>
            <h3 class="status"><div class="dead"></div>{people?.results[7].status}</h3>

            <h3 class="locationLabel">Last known location</h3>
            <h3 class="location"><a href="/location">{people?.results[7].location?.name}</a></h3>
        </div>
    </div>

    <div class="card">
        <img class="image" src={people?.results[10]?.image} />
        <div class="info">
            <h1 class="name">{people?.results[10]?.name}</h1>
            <h3 class="status"><div class="dead"></div>{people?.results[10].status}</h3>

            <h3 class="locationLabel">Last known location</h3>
            <h3 class="location"><a href="/location">{people?.results[10].location?.name}</a></h3>
        </div>
    </div>

    <div class="card">
        <img class="image" src={people?.results[4]?.image} />
        <div class="info">
            <h1 class="name">{people?.results[4]?.name}</h1>
            <h3 class="status"><div class="alive"></div>{people?.results[4].status}</h3>

            <h3 class="locationLabel">Last known location</h3>
            <h3 class="location"><a href="/location">{people?.results[4].location?.name}</a></h3>
        </div>
    </div>

    <div class="card">
        <img class="image" src={people?.results[19]?.image} />
        <div class="info">
            <h1 class="name">{people?.results[19]?.name}</h1>
            <h3 class="status"><div class="unknown"></div>{people?.results[19].status}</h3>

            <h3 class="locationLabel">Last known location</h3>
            <h3 class="location"><a href="/location">{people?.results[19].location?.name}</a></h3>
        </div>
    </div>
</div>

<style>

    .grid{
        display:grid;
        grid-template-columns:1fr 1fr 1fr;
        gap:30px;
    }

    .card{
        background:#333;
        overflow:hidden;
        height:240px;
        display:flex;      
        border-radius:20px;  
    }

    .image{
        width:30%;
        background-size:cover;
        background-position:center;
    }

    .info{
        padding-left:20px;
        padding-right:20px;
        padding-top:10px;
        padding-bottom:15px;
    }

    .dead{
        background:firebrick;
        width:10px;
        height:10px;
        border-radius:100%;
        margin-right:10px;
    }
    .alive{
        background:green;
        width:10px;
        height:10px;
        border-radius:100%;
        margin-right:10px;
    }
    .unknown{
        background:grey;
        width:10px;
        height:10px;
        border-radius:100%;
        margin-right:10px;
    }

    .name{
        font-family:sans-serif;
        color:white;
    }

    .status{
        font-family:sans-serif;
        color:white;
        display:flex;
        align-items:center;
    }

    .locationLabel{
        color:#777;
        font-family:sans-serif;
        font-size:16px;
        margin:0 0 5px;        
    }

    .location{
        color:white;
        font-family:sans-serif;
        font-size:16px;
        margin-bottom:20px;
        margin-left:0;
        margin-right:0;
        margin-top:0;
        margin-bottom:5px;
    }

    .location a{
        color:white;
        font-family:sans-serif;
        font-size:16px;
        margin-bottom:20px;
        margin-left:0;
        margin-right:0;
        margin-top:0;
        margin-bottom:5px;
    }


</style>