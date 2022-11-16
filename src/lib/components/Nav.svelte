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
        width: 25px;
        height: 25px;

        color: rgb(235, 159, 88);
        padding: 30px;
        position: relative;
    }

    .selected-page:after {
        content: "";
        display: block;
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 3px;

        background-color: rgb(235, 159, 88);
    }

    .navigation {
        display: flex;
        flex-direction: column;

        position: fixed;
        top: 0;
        left: 0;

        height: 100vh;
        background-color: rgb(20, 20, 20);
    }
</style>