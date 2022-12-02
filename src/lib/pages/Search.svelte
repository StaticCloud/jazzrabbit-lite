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
            <div class="titleWrapper">
                <h3 class="title">{album.collectionName}</h3>
                <p class="plus"><FaPlus/></p>
            </div>
            <p class="albumArtist">{album.artistName}</p>
        </div>
    {/each}
{/if}
</div>

<style>
    h3 {
        margin: 10px 0;
    }

    .titleWrapper {
        display: flex;
        flex-wrap: flex;
    }

    .title {
        flex: 1;
    }

    .plus {
        color: rgb(75, 75, 75);
        display: block;
        width: 25px;
        height: 25px;

        margin: 10px 0;

        padding: 5px;
    }

    .grid {
        padding: 25px;
        display: grid;
        gap: 10px;
        grid-row: 1;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    }

    .albumWrapper {
        background-color: rgb(29, 29, 29);
        padding: 10px;

        border-bottom: 3px solid rgb(235, 159, 88);
    }

    .albumArtist {
        padding-bottom: 40px;
    }
</style>