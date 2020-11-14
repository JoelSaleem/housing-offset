<script>
  export let val;
</script>

<div class="container">
  <div>offset</div>
  <input type="number" bind:value="{val}" placeholder="offset" />
</div>

<style>
  .container {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  input {
    display: flex;
    margin: 0em 1em;
    padding: 0.2em 0em;
  }
</style>
