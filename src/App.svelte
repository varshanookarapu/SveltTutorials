<script>
  import Navbar from "./lib/Navbar.svelte";
  import Search from "./lib/Search.svelte";
  import TvShow from "./lib/TvShow.svelte";
  import { onMount } from "svelte";

  let shows = [];
  let queryString;

  onMount(() => {
    getTvShows();
  });

  function getTvShows() {
    fetch(`https://api.tvmaze.com/search/shows?q=girls`)
      .then((response) => response.json())
      .then((data) => {
        shows = data;
        console.log(shows);
      });
  }
</script>

<Navbar />
<main class="container mt-5">
  <Search {queryString} />
  <div class="d-flex gap-4 flex-wrap justify-content-between">
    {#each shows as show}
      <TvShow show={show.show} />
    {/each}
  </div>
</main>

<style>
</style>
