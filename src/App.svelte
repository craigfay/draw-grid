<script>
  $: grid = [
    [0,0,0,0],
    [0,0,0,0],
    [0,0,0,0],
    [0,0,0,0],
  ]
  // Negate the value of a particular coordinate
  function toggleSquare(y, x) {
    grid[y][x] = +!grid[y][x];
    console.log(grid)
  }
</script>

{#each grid as row, y}
  <div class="row">
    {#each row as square, x}
      <div
        class="square { square ? "enabled" : ""}"
        on:click={() => toggleSquare(y, x)}>
      </div>
    {/each}
  </div>
{/each}

<style>
  .row {
    display: flex;
    flex-direction: row;
  }
  .square {
    width: 32px;
    height: 32px;
    margin: 4px;
    background-color: gainsboro;
  }
  .square.enabled{
    background-color: red;
  }
</style>