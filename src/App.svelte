<script>
  import Header from './Header.svelte';
  let name = 'world';

  function setName({ target }) {
    const { value } = target;

    name = value || 'world';

    console.log(value);
  }
</script>

<main>
  <Header />
  <div>
    <input type="text" placeholder="Enter your name" on:keyup={setName} />
    <h1>Hello {name}!</h1>
  </div>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  div {
    margin-top: 25px;
  }
</style>
