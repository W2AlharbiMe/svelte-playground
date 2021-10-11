<script>
  import Header from './Header.svelte';
  import MainComponent from './dispatch/main.svelte';

  let name = 'world';
  const links = [
    ['Home', '#'],
    ['About', '#about'],
    ['Link', '#external'],
  ];

  function setName({ target }) {
    const { value } = target;

    name = value || 'world';
  }
</script>

<main>
  <Header {links} />
  <div>
    <h1>Hello {name}!</h1>
    <input type="text" placeholder="Enter your name" on:keyup={setName} />
  </div>

  <MainComponent />
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
