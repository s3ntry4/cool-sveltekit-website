<script>
  import Hlink from "$lib/Links.svelte"

  let pressed = 0;

  function pressbutton() {
    pressed++;
  }

  function unpressbuttion() {
    pressed--;
  }
</script>

<title>counter</title>

<h1 class="text-2xl font-bold">counter</h1>
<button on:click={pressbutton} class="btn">increase counter</button>
<button on:click={unpressbuttion} class="btn">decrease counter</button>
<p>counter: {pressed}</p>