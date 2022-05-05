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

<h1 class="text-2xl font-bold">counter</h1>
<button on:click={pressbutton}>increase counter</button>
<button on:click={unpressbuttion}>decrease counter</button>
<p>counter: {pressed}</p>