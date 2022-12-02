<script>
    let favorites = localStorage.getItem("favorites");
</script>

{#if favorites}
    <p>favorites</p>
{:else}
    <p>No favorites</p>
{/if}