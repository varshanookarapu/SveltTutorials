<script>
  import Navbar from "./lib/Navbar.svelte";
  import TvShow from "./lib/TvShow.svelte";
  import { onMount } from "svelte";

  let shows = [];

  onMount(() => {
    getTvShows();
  });

  function getTvShows() {
    fetch(`https://api.tvmaze.com/search/shows?q=robot`)
      .then((response) => response.json())
      .then((data) => {
        shows = data;
        console.log(shows);
      });
  }
</script>

<Navbar />
<main class="container mt-5">
  <div class="d-flex gap-4 flex-wrap">
    {#each shows as show}
      <TvShow />
    {/each}
  </div>
</main>

<style>
</style>
