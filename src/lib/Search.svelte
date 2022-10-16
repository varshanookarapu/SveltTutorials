<!-- event.stopPropagation() -->
<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  let searchValue;
  function onSearch(event) {
    event.preventDefault();
    dispatch("search", searchValue);
  }
</script>

<!-- <div class="d-flex ">
  <input class="flex-grow-1" type="text" placeholder="Search Tv Showzzz..." />
  <button class="btn btn-primary">Search</button>
</div> -->

<!-- create a search component
add search input box along with search button
onClick of Search button  it should fire an event  -->

<form class="d-flex mb-3 gap-3 " on:submit={onSearch} role="search">
  <input
    class="form-control flex-grow-1"
    type="search"
    placeholder="Search Tv Showzzz..."
    aria-label="Search"
    bind:value={searchValue}
  />
  <button class="btn btn-success" type="submit">Search</button>
</form>
