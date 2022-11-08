<script>
    let albumData;
    import SearchBar from '../components/SearchBar.svelte'
    import Album from '../components/Album.svelte'
</script>

<SearchBar bind:searchResults="{albumData}"/>
<div class="grid">
{#if albumData}
    {#each albumData as album}
        <Album cover={album.artworkUrl100.replace('100x100', '300x300')}></Album>
    {/each}
{/if}
</div>

<style>
    .grid {
        display: grid;
        gap: 10px;
        grid-row: 1;
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
</style>