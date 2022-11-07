<script lang="ts">
    let query;

    const getMusic = async () => {
        query = query.split(" ").join("+");
        const response = await fetch(`https://itunes.apple.com/search?country=US&term=${query}&media=music&entity=album`);
        const data = await response.json();
        console.log(data);
    }
    
</script>

<div>
    <form on:submit|preventDefault={() => getMusic()}>
        <label for="music-search">Search for music:</label>
        <input id="music-search" bind:value={query}/>
        <button type="submit">Submit</button>
    </form>
</div>