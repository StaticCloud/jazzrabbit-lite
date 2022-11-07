<script lang="ts">
  import Router from 'svelte-spa-router';

  // pages
  import Home from './lib/pages/Home.svelte';
  import Search from './lib/Search.svelte';
  import Collection from './lib/pages/Collection.svelte';
  import Favorites from './lib/pages/Favorites.svelte';
  import NotFound from './lib/pages/NotFound.svelte';

  // components
  import Nav from './lib/components/Nav.svelte'

  const routes = {
    '/': Home,
    '/search': Search,
    '/collection': Collection,
    '/Favorites': Favorites,
    '*': NotFound,
  }
</script>

<main>
  <Nav/>
  <Router {routes}/>
</main>

<style>
</style>