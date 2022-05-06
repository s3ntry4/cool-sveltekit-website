<script>
	import Hlink from "$lib/Links.svelte"
  var todos = [
    {text: "do stuff", complete: false}
  ];
  var itext = "";
  function addtodo() {
    if(itext != "") {
      todos = [...todos, {text: itext, complete: false}]
      itext = "";
    }
  }
  function subtodo(i) {
    todos.splice(i, 1)
    todos = todos;
  }
  function dotodo(i) {
    todos[i].complete = !todos[i].complete
  }
</script>

<title>to do list</title>

<h1 class="text-3xl font-bold">
	to do list
</h1>

<form on:submit|preventDefault={addtodo}>
<input type="text" bind:value={itext} />
<input type="submit" class="btn cursor-pointer" value="add item" />
</form>

<ul class="margin">

{#each todos as todo, i}
<li class="cursor-default">
  <input type="checkbox" class="cursor-pointer" bind:checked={todo.complete} />
  <span class:line-through={todo.complete} class:text-gray-500={todo.complete}>
    {todo.text}
  </span>
  {#if todo.complete}
    <button class="text-red-400" on:click={() => {subtodo(i)}}>X</button>
  {/if}
</li>
{/each}

</ul>