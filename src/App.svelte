<script>
  $: grid = [
    [0,0,0,0],
    [0,0,1,0],
    [0,0,0,0],
    [0,0,0,0],
  ]
</script>

{#each grid as row}
  <div class="row">
    {#each row as square}
      <div class="square { square ? "enabled" : ""}"></div>
    {/each}
  </div>
{/each}

<style>
  .row {
    display: flex;
    flex-direction: row;
  }
  .square {
    width: 50px;
    height: 50px;
    margin: 5px;
    background-color: gainsboro;
  }
  .square.enabled{
    background-color: red;
  }
</style>