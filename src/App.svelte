<script>
  import Header from './Header.svelte';
  export let name = 'world';
</script>

<main>
  <Header />

  <h1>Hello {name}!</h1>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }
</style>
