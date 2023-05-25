<script>
import { onMount } from "svelte";

const BASE_URL = "https://rickandmortyapi.com/api";
let people;
let d;
onMount(async () => {
        const f = await fetch(`${BASE_URL}/location`);
        d = await f.json();
        console.log(d);
        people = d
    })
</script>

<span>{people?.results[0]?.name}</span>