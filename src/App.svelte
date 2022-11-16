<script lang="ts">
  import Router from 'svelte-spa-router';

  // pages
  import Home from './lib/pages/Home.svelte';
  import Search from './lib/pages/Search.svelte';
  import Collection from './lib/pages/Collection.svelte';
  import Favorites from './lib/pages/Favorites.svelte';
  import NotFound from './lib/pages/NotFound.svelte';

  // components
  import Nav from './lib/components/Nav.svelte'

  const routes = {
    '/': Home,
    '/search': Search,
    '/collection': Collection,
    '/favorites': Favorites,
    '*': NotFound,
  }
</script>

<main>
  <Nav/>
  <section class="content-wrap">
    <Router {routes}/>
  </section>
</main>

<style>
  .content-wrap {
    padding-left: 85px;
    height: 100vh;
  }
</style>