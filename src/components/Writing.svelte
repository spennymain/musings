<script>
  import { fly } from 'svelte/transition';
  let visible = false;
</script>

<div>
  <h2>a collection of writings - accumulated over time.</h2> 
  <div class="buttons">
    <button on:click={() => visible = !visible}>on ukraine</button>
  </div>
  {#if visible}
  <p transition:fly="{{ y: 200, duration: 2000 }}">
  incoming content
  </p>
  {/if}
</div>

<style>
  h2, p {
    text-align: center;
  }
  .buttons button {
    padding: 0.25% 5%;
  }
</style>
