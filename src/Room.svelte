<script>
  export let cost;
  export let title;
</script>

<div class="container">
  <div>{title}</div>
  <input class="room" value="{cost}" disabled />
</div>

<style>
  .container {
    padding: 2em;
  }

  input {
    background-color: lightgrey;
    color: black;
  }
</style>
