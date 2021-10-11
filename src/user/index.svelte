<script>
  import { outro_and_destroy_block } from 'svelte/internal';

  import { user } from '../store/user';
  import Login from './Login.svelte';

  let username = '';
  let password = '';
  let loggedIn;

  user.subscribe((u) => {
    username = u.username;
    loggedIn = u.loggedIn;
  });

  function logout(e) {
    user.update((u) => ({ loggedIn: false, username: '' }));
  }
</script>

<main>
  {#if loggedIn}
    <h4>Welcome, {username}</h4>

    <button on:click|preventDefault={logout}>Logout</button>
  {:else}
    <Login />
  {/if}
</main>
