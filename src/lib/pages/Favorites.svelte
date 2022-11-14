<script>
    let favorites = localStorage.getItem("favorites");
</script>

<h1>Favorites</h1>
{#if favorites}
    <p>favorites</p>
{:else}
    <p>No favorites</p>
{/if}