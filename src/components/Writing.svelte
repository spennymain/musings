<script>
  import { fly } from 'svelte/transition';
  let visible_ukr = false;
  let visible_canada = false;

</script>

<div>
  <h2>a collection of writings - accumulated over time.</h2> 
  <div class="buttons">
    <button on:click={() => visible_ukr = !visible_ukr}>on ukraine</button>
    <button on:click={() => visible_canada = !visible_canada}>on canadian democracy</button>
  </div>
  {#if visible_ukr}
  <div transition:fly="{{ y: 200, duration: 2000 }}">
    <h3>many things have changed since d-0</h3>
    <p>as we approach d-5 there exists hope, faith for the good, contrasted by loss, destruction.</p>
  </div>
  {/if}
  {#if visible_canada}
  <div transition:fly="{{ y: 200, duration: 2000 }}">
    <h3>the importance of honest leadership and the weakness of democracy</h3>
    <p>I find myself, and others, thinking of the government as an entity of control in constant conflict against the will of the people. But democracy <i>is</i> the people, there is no other way about it.</p>
  </div>
  {/if}
</div>

<style>
  h2, div{
    text-align: center;
  }
  .buttons button {
    padding: 0.25% 5%;
    font-size: large;
  }
</style>
