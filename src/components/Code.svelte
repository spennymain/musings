<script>
  import { onMount } from 'svelte';

  let repos = [];
  let pinnedRepos = ['musings', 'communauto_ex', 'bitwitg', 'telecommunist-manifesto', 'vim', 'qmk_firmware']

  onMount(async () => {
      const res = await fetch('https://api.github.com/users/spennymain/repos', {
          headers: {"Accept": "application/vnd.github.v3+json"}
      });
      repos = await res.json()
  });

  function getReadme(repo) {
      fetch(`https://api.github.com/repos/spennymain/${repo}/readme`, {
          headers: {"Accept": "application/vnd.github.v3+json"}
        }).then(res => res.json()).then(data => atob(data.content))
  }

</script>

<h1>git repos</h1>
<div>
  {#each repos as repo}
    {#if pinnedRepos.includes(repo.name)}
    <div class="innerdiv">
      <a href={repo.html_url}>
        <h3>{repo.name}</h3>
      </a>
      <p>{getReadme(repo.name)}</p>
    </div>
    {/if}
  {:else}
    <p>loading...</p>
  {/each}
</div>

<style>
  div {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
  }
  .innerdiv {
    display: flex;
    flex-direction: column;
  }
  a {
    color: white;
  }
  h1, p {
    text-align: center
  }
</style>
