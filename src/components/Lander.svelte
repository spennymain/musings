<script>
  import { onMount } from 'svelte';

  let ip= '';
  let revGeo = '';
  let sarcasm= '';
  onMount(async () => {
    const ipRes = await fetch(`https://api.ipify.org/`).then()
    ip = await ipRes.text();
    navigator.geolocation.getCurrentPosition(position =>
        revGeo = position.coords);

    });

  function handleClick() {
    sarcasm = "just kidding. i really don't care."
    setTimeout(function() {
      window.location.href ='/portfolio'
    }, 250)
  }

</script>

<div>
  {#if ip && revGeo}
  <h1>Welcome {ip}</h1>
  <p>I see you're using <code>{navigator.userAgent}</code> to connect...it's not my favourite config, but i guess it works.</p>
  <h3>How's the weather at {revGeo.latitude}, {revGeo.longitude} ?</h3>
  <div class="buttons">
    <button on:click={handleClick}>good</button>
    <button on:click={handleClick}>bad</button>
  </div>
  <p>{sarcasm}</p>
  {:else}
    <p>collecting some details...</p>
  {/if}
</div>

<style>
  h1, h3, p{
    margin: 0;
    text-align: center;
  }
  h3 {
    margin-top: 1%;
  }
  .buttons button {
    width: 5%;
    padding: 0.25% 1%;
  }

</style>
