<script>
  import router from "page";
  import Lander from './components/Lander.svelte';
  import Shell from './components/Shell.svelte';
  import Portfolio from './components/Portfolio.svelte';
  import About from './components/About.svelte';
  import Code from './components/Code.svelte';
  import Writing from './components/Writing.svelte';

  let page;

  router('/', () => page = Lander)
  router('/shell', () => page = Shell)
  router('/portfolio', () => page = Portfolio)
  router('/about', () => page = About)
  router('/code', () => page = Code)
  router('/writing', () => page = Writing)
  router.start()
</script>

<main>
  <svelte:component this={page} />
</main>

<style>
</style>
