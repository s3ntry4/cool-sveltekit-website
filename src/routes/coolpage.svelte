<script>
  import Hlink from "$lib/Links.svelte"

  let pressed = 0;

  function pressbutton() {
    pressed++;
  }
</script>

<h1 class="text-2xl font-bold">cool page</h1>
<button on:click={pressbutton} class="btn">cool button</button>
<p>the button has been pressed {pressed} time(s)</p>