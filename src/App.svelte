<script>
  import Room from "./Room.svelte";
  import Offset from "./Offset.svelte";

  export let name;
  let cost = 0;
  let offset12 = 0;
  let offset23 = 0;

  let room1Cost = 0;
  let room2Cost = 0;
  let room3Cost = 0;

  $: {
    if ([cost, offset12, offset23].some((v) => isNaN(v))) {
      cost = 0;
      offset12 = 0;
      offset23 = 0;
    }
    cost = +cost;
    offset12 = +offset12;
    offset23 = +offset23;

    room1Cost = (cost - offset23 - 2 * offset12) / 3;
    room2Cost = room1Cost + offset12;
    room3Cost = room2Cost + offset23;
  }
</script>

<main>
  <h1>Housing Offset</h1>
  
  <h2>Total house cost</h2>
  <input bind:value="{cost}" />

  <Room cost={room3Cost} title="Third Room" />

  <Offset bind:val="{offset23}" />
  
  <Room cost={room2Cost} title="Second Room" />
  
  <Offset bind:val="{offset12}" />

  <Room cost={room1Cost} title="First Room" />

  <div>tot: {room1Cost + room2Cost + room3Cost}</div>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
	background: #313131;
	color: #d0d0d0;
    height: 100%;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
