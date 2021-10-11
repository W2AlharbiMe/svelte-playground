<script>
  import { user } from '../store/user';

  let username = '';
  let password = '';

  let error = {
    message: 'Invalid Credentials.',
    show: false,
  };

  function handleLogin(e) {
    if (username === 'admin' && password === '123') {
      user.update((u) => ({ loggedIn: true, username }));
    } else {
      error.show = true;
    }
  }
</script>

{#if error.show}
  <div>
    <span style="color: red">{error.message}</span>
  </div>
{/if}

<div>
  <label for="username">Username:</label>
  <input type="text" placeholder="admin" bind:value={username} />
</div>

<div>
  <label for="password">Password:</label>
  <input type="text" placeholder="123" bind:value={password} />
</div>

<button on:click|preventDefault={handleLogin}>Login!</button>
