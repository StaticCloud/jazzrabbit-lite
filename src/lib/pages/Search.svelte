<script>
    let albumData;

    import FaPlus from 'svelte-icons/fa/FaPlus.svelte'

    import SearchBar from '../components/SearchBar.svelte'
    import Album from '../components/Album.svelte'
</script>

<SearchBar bind:searchResults="{albumData}"/>
<div class="grid">
{#if albumData}
    {#each albumData as album}
        <div class="albumWrapper">
            <Album cover={album.artworkUrl100.replace('100x100', '250x250')}></Album>
            <h3>{album.collectionName}</h3>
            <p class="albumArtist">{album.artistName}</p>
            <p class="plus"><FaPlus/></p>
        </div>
    {/each}
{/if}
</div>

<style>
    h3 {
        margin: 10px 0;
    }

    .plus {
        color: rgb(235, 159, 88);
        flex: 1;
        width: 25px;
        height: 25px;

        position: absolute;
        bottom: 0;

        padding: 10px;

        background-color: rgb(29, 29, 29);

        border-radius: 25px;
    }

    .grid {
        padding: 25px;
        display: grid;
        gap: 10px;
        grid-row: 1;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    }

    .albumWrapper {
        position: relative;
        padding: 10px;
    }

    .albumArtist {
        padding-bottom: 40px;
    }
</style>