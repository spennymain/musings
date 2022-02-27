<script>
  import router from "page";
  import Lander from './components/Lander.svelte';
  import Shell from './components/Shell.svelte';
  import Portfolio from './components/Portfolio.svelte';

  let page;

  router('/', () => page = Lander)
  router('/shell', () => page = Shell)
  router('/portfolio', () => page = Portfolio)
  router.start()
</script>

<main>
  <svelte:component this={page} />
</main>

<style>
</style>
