<script lang="ts">
  import Router from 'svelte-spa-router';

  import Home from './lib/pages/Home.svelte';
  import Search from './lib/Search.svelte';
  import NotFound from './lib/pages/NotFound.svelte';

  const routes = {
    '/': Home,
    '/search': Search,
    '*': NotFound,
  }
</script>

<main>
  <Router {routes}/>
</main>

<style>
</style>