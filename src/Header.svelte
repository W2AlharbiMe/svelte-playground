<script>
  export let links;
</script>

<main>
  <nav>
    {#each links as [text, path]}
      <a href={path}>{text}</a>
    {/each}
  </nav>
</main>

<style>
  nav {
    display: inline-block;
  }

  nav a {
    margin-left: 15px;
    margin-right: 15px;
  }
</style>
