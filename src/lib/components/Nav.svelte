<script lang="ts">
    import { link } from 'svelte-spa-router'
</script>

<nav>
    <a href="/" use:link>Home</a>
    <a href="/search" use:link>Search</a>
    <a href="/collection" use:link>Collection</a>
    <a href="/favorites" use:link>Favorites</a>
</nav>