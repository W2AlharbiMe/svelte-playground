<script>
  import Inner from './Inner.svelte';

  function handleMessage({ detail: payload }) {
    console.log('Fired Message,', payload);
  }
</script>

<Inner on:message={handleMessage} />
