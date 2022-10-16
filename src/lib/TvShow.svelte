<script>
  export let show;
  console.log(show);
</script>

<div class="card">
  <img src={show.image?.medium} class="card-img-top" alt="..." />
  <div class="card-body d-flex-column">
    <h5 class="card-title">{show.name}</h5>
    {#each show.genres as genre}
      <span class="badge text-bg-primary me-1">{genre}</span>
    {/each}
    <p class="card-text">{show.language}</p>

    <div class="d-flex gap-2 justify-content-between">
      <span>Rating: {show.rating.average || "NA"}</span>
      <a href={show.url} class="btn btn-primary" target="_blank">Go to Show!!</a
      >
    </div>
  </div>
</div>

<style>
  .card {
    width: 18rem;
    box-shadow: rgb(0 0 0) 6px 7px 11px;
    border: 0;
    background-color: rgb(43, 43, 43);
    color: white;
    transform: scale(0.9);
    transition: all 0.5s ease-out;
  }

  .card:hover {
    background-color: beige;
    color: black;
    opacity: 3;
    transform: scale(1);
  }
  .card-text {
    padding: 5px 2px;
  }
</style>
