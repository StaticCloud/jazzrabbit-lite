<script>
    let albumData;
    import SearchBar from '../components/SearchBar.svelte'
    import Album from '../components/Album.svelte'
</script>

<h1>Search</h1>
<SearchBar bind:searchResults="{albumData}"/>
<div class="grid">
{#if albumData}
    {#each albumData as album}
        <div class="albumWrapper">
            <Album cover={album.artworkUrl100.replace('100x100', '250x250')}></Album>
            <h3>{album.collectionName}</h3>
            <p>{album.artistName}</p>
        </div>
    {/each}
{/if}
</div>

<style>
    h3 {
        margin: 10px 0;
    }

    .grid {
        padding: 25px;
        display: grid;
        gap: 10px;
        grid-row: 1;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    }

    .albumWrapper {
        padding: 10px;
    }
</style>