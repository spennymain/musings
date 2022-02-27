<script>
  import router from "page"
  import Lander from './components/Lander.svelte'

  let page;

  router('/', () => page = Lander)
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
