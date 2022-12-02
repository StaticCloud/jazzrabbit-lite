<script lang="ts">
    import FaSearch from 'svelte-icons/fa/FaSearch.svelte'

    export let searchResults;
    let query: String;

    const getMusic = async () => {
        if (query) {
            query = query.split(" ").join("+");
            let response = await fetch(`https://itunes.apple.com/search?country=US&term=${query}&media=music&entity=album`);
            let { results } = await response.json();
            searchResults = results;
            query = '';
            console.log(searchResults);
        }
    }
</script>

<div>
    <form on:submit|preventDefault={() => getMusic()}>
        <input id="music-search" placeholder="Search for albums" bind:value={query}/>
        <button type="submit"><FaSearch/></button>
    </form>
</div>

<style>
    form { 
        position: relative;
        display: inline-block;
    }

    input {
        background-color: rgb(29, 29, 29);
        border: none;
        padding: 20px;

        margin: 20px;
        color: white;
        border-radius: 70px;
    }

    input:focus {
        border-color: rgb(75, 75, 75);
    }

    button {
        width: 20px;
        margin: 20px;
        display: block;

        top: 0;
        bottom: 0;
        position: absolute;
        right: 15px;

        border-radius: 70px;

        color: rgb(75, 75, 75);
    }

    button:hover {
        transition: all 0.2s;
        color: rgb(235, 159, 88);
    }
</style>