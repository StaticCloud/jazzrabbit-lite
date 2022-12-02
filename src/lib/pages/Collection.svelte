<script>
    let collection = localStorage.getItem("collection");
</script>

{#if collection}
    <p>collection</p>
{:else}
    <p>No collection</p>
{/if}