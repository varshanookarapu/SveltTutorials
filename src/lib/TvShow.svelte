<script>
  export let show;
  console.log(show);
</script>

<div class="card">
  <img src={show.image.medium} class="card-img-top" alt="..." />
  <div class="card-body">
    <h5 class="card-title">{show.name}</h5>
    {#each show.genres as genre}
      <span class="badge text-bg-primary me-1">{genre}</span>
    {/each}
    <p class="card-text">{show.language}</p>
    <span>Rating: {show.rating.average}</span>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<style>
  .card {
    width: 18rem;
    box-shadow: rgb(0 0 0) 6px 7px 11px;
    border: 0;
  }
</style>
