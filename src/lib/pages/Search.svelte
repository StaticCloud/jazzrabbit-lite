<script>
    let albumData;
    import SearchBar from '../components/SearchBar.svelte'
</script>

<SearchBar bind:searchResults="{albumData}"/>
<div class="grid">
{#if albumData}
    {#each albumData as album}
        <div class="item"></div>
        <!-- <img alt={album.collectionType} src={album.artworkUrl100.replace('100x100', '300x300')}/> -->
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

    .item {
        background-color: burlywood;
        aspect-ratio: 1;
    }
</style>