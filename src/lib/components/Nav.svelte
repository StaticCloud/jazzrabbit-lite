<script lang="ts">
    import FaHome from 'svelte-icons/fa/FaHome.svelte'
    import FaSearch from 'svelte-icons/fa/FaSearch.svelte'
    import FaBook from 'svelte-icons/fa/FaBook.svelte'
    import FaHeart from 'svelte-icons/fa/FaHeart.svelte'

    import NavLink from './NavLink.svelte';

    let currentPage = 'home';

</script>

<nav class="navigation">
    <NavLink href='/' page="home" currentPage={currentPage}> 
        <FaHome/>
    </NavLink>
    <NavLink href='/search' page="search" currentPage={currentPage}>
        <FaSearch/>
    </NavLink>
    <NavLink href='/collection' page="collection" currentPage={currentPage}>
        <FaBook/>
    </NavLink>
    <NavLink href='/favorites' page="favorites" currentPage={currentPage}>
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
        background-color: rgb(22, 22, 22);
    }
</style>