<script>
    let albumData;

    import { fly } from 'svelte/transition';
    import FaPlus from 'svelte-icons/fa/FaPlus.svelte'

    import SearchBar from '../components/SearchBar.svelte'
    import Album from '../components/Album.svelte'
</script>

<SearchBar bind:searchResults="{albumData}"/>
{#key albumData}
    <div class:grid="{albumData}" class="wrap">
        {#if albumData}
            {#each albumData as album, i}
                <div class="albumWrapper" in:fly="{{ y: -20, duration: 400, delay: i * 100 }}">
                    <Album cover={album.artworkUrl100.replace('100x100', '250x250')}></Album>
                    <div class="titleWrapper">
                        <h3 class="title">{album.collectionName}</h3>
                        <p class="plus"><FaPlus/></p>
                    </div>
                    <p class="albumArtist">{album.artistName}</p>
                </div>
            {/each}
        {:else}
                <h1 in:fly="{{ x: 50, duration: 500 }}">For example, "David Bowie" or "The Wall"</h1>
        {/if}
    </div>
{/key}

<style>
    h3 {
        margin: 10px 0;
    }

    h1 { 
        margin: 20px;
        font-size: 3em;
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
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
    }

    .albumWrapper {
        background-color: rgb(29, 29, 29);
        padding: 10px;

        border-bottom: 3px solid rgb(235, 159, 88);
    }

    .albumArtist {
        padding-bottom: 40px;
    }

    .wrap {
        overflow-x: hidden;
    }
</style>