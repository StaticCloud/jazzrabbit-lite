<script lang="ts">
    export let searchResults;
    let query: String;

    const getMusic = async () => {
        query = query.split(" ").join("+");
        let response = await fetch(`https://itunes.apple.com/search?country=US&term=${query}&media=music&entity=album`);
        let { results } = await response.json();
        searchResults = results;
        console.log(results);
    }
</script>

<div>
    <form on:submit|preventDefault={() => getMusic()}>
        <label for="music-search">Search for music:</label>
        <input id="music-search" bind:value={query}/>
        <button type="submit">Submit</button>
    </form>
</div>