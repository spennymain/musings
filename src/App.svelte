<script>
  import router from "page";
  import Lander from './components/Lander.svelte';
  import Shell from './components/Shell.svelte';

  let page;

  router('/', () => page = Lander)
  router('/shell', () => page = Shell)
  router.start()
</script>

<main>
  <svelte:component this={page} />
</main>

<style>
  main {
    background: black;
  }
</style>
