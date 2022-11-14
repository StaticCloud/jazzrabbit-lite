<script lang="ts">
    import { link } from 'svelte-spa-router'
</script>

<nav class="navigation">
    <a href="/" use:link>Home</a>
    <a href="/search" use:link>Search</a>
    <a href="/collection" use:link>Collection</a>
    <a href="/favorites" use:link>Favorites</a>
</nav>

<style>
    .navigation {
        display: flex;
        flex-direction: column;

        position: fixed;
        top: 0;
        left: 0;
        width: 90px;

        height: 100vh;
        background-color: rgb(43, 43, 43);
    }
</style>