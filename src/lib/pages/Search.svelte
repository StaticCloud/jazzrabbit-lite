<script>
    let albumData;
    import SearchBar from '../components/SearchBar.svelte'
</script>

<SearchBar bind:searchResults="{albumData}"/>
{#if albumData}
    {#each albumData.results as album}
        <p>{album.collectionName}</p>
    {/each}
{/if}