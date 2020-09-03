<script>
  export let addTodo;
  let value = '';
</script>

<style>
  input {
    width: 100%;
    padding: 0.5rem 1rem;
    margin: 1rem 0;
  }

  button {
    width: 100%;
    padding: 0.5rem 1rem;
    background: rgb(43, 122, 226);
    color: white;
  }
</style>

<input bind:value />
<button on:click={addTodo(value)}>Add Todo</button>
