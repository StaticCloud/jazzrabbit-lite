<script lang="ts">
    import { link } from 'svelte-spa-router'
    import FaHome from 'svelte-icons/fa/FaHome.svelte'
    import FaSearch from 'svelte-icons/fa/FaSearch.svelte'
    import FaBook from 'svelte-icons/fa/FaBook.svelte'
    import FaHeart from 'svelte-icons/fa/FaHeart.svelte'

    import NavLink from './NavLink.svelte';

    let activePage = '';
    let currentPage = 'home';

</script>

<nav class="navigation">
    <NavLink href='/'>
        <FaHome/>
    </NavLink>
    <NavLink href='/search'>
        <FaSearch/>
    </NavLink>
    <NavLink href='/collection'>
        <FaBook/>
    </NavLink>
    <NavLink href='/favorites'>
        <FaHeart/>
    </NavLink>
</nav>

<style>
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