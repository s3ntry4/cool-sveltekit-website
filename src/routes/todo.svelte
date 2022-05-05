<script>
	import Hlink from "$lib/Links.svelte"
  var todos = [
    "cool thing"
  ];
  var itext = "";
  function addtodo() {
    todos.unshift(itext);
    todos = todos;
    itext = "";
  }
</script>

<title>todo list</title>

<h1 class="text-3xl font-bold">
	to do list
</h1>

<input type=text bind:value={itext} />
<button on:click={addtodo}>add item</button>

<ul>

{#each todos as todo}
<li>{todo}</li>
{/each}

</ul>