<script>
  import Header from './Header.svelte';
  import MainComponent from './dispatch/main.svelte';
  import Login from './user/index.svelte';

  let name = 'world';
  const links = [
    ['Home', '#'],
    ['About', '#about'],
    ['Link', '#external'],
  ];

  function handleMessage({ detail: payload }) {
    const { text } = payload;

    console.log('Hello', name || text);
  }
</script>

<main>
  <Header {links} />
  <div>
    <h1>Hello {name}!</h1>
    <input type="text" placeholder="Enter your name" bind:value={name} />
  </div>

  <MainComponent on:message={handleMessage} />

  <hr />

  <Login />
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
