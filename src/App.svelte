<script lang="ts">
  import Router from 'svelte-spa-router';

  import Search from './lib/Search.svelte';

  const routes = {
    '/search': Search
  }
</script>

<main>
  <Router {routes}/>
</main>

<style>
</style>