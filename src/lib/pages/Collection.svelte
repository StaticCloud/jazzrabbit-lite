<script>
    let collection = localStorage.getItem("collection");
</script>

<h1>Collection</h1>
{#if collection}
    <p>collection</p>
{:else}
    <p>No collection</p>
{/if}