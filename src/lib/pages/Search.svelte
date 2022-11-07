<script>
    let albumData;
    import SearchBar from '../components/SearchBar.svelte'
</script>

<SearchBar bind:searchResults="{albumData}"/>
{#if albumData}
    {#each albumData as album}
        <img alt={album.collectionType} src={album.artworkUrl100.replace('100x100', '300x300')}/>
    {/each}
{/if}