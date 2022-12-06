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
        background-color: white;
        border: none;
        padding: 15px;

        margin: 25px 25px 0px 25px;
        border-radius: 70px;
    }

    button {
        width: 20px;
        margin: 20px 20px 0px 20px;
        display: block;

        top: 0;
        bottom: 0;
        position: absolute;
        right: 15px;

        border-radius: 70px;
    }
</style>