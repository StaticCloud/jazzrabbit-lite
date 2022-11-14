<script lang="ts">
    import { link } from 'svelte-spa-router'
    import FaHome from 'svelte-icons/fa/FaHome.svelte'
    import FaSearch from 'svelte-icons/fa/FaSearch.svelte'
    import FaBook from 'svelte-icons/fa/FaBook.svelte'
    import FaHeart from 'svelte-icons/fa/FaHeart.svelte'
</script>

<nav class="navigation">
    <a href="/" use:link>
        <FaHome/>
    </a>
    <a href="/search" use:link>
        <FaSearch/>
    </a>
    <a href="/collection" use:link>
        <FaBook/>
    </a>
    <a href="/favorites" use:link>
        <FaHeart/>
    </a>
</nav>

<style>
    a {
        width: 31px;
        height: 31px;

        color: rgb(214, 141, 73);
        padding: 25px;
    }

    .navigation {
        display: flex;
        flex-direction: column;

        position: fixed;
        top: 0;
        left: 0;

        height: 100vh;
        background-color: rgb(43, 43, 43);
    }
</style>