<script>
  import { onMount } from 'svelte';

  let ip= '';
  onMount(async () => {
    const res = await fetch(`https://api.ipify.org/`).then()
    ip = await res.text();
  })
</script>

<div>
  {#if ip}
  <h1>Welcome {ip}</h1>
  <h3>How's the weather in {navigator.geolocation}</h3>
  <p>I see you're using {navigator.userAgent} to connect...</p>
  {:else}
    <h1>Welcome</h1>
  {/if}
</div>

<style>
  h1, h3, p{
    text-align: center;
    margin: 0
  }

</style>
