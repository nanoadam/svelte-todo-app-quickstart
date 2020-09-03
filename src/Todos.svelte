<script>
  export let todos;

  export let getTodos;

  getTodos();
</script>

<style>
  h3 {
    margin: 1rem 0;
    background: blueviolet;
    padding: 1rem;
    color: white;
  }
  .todo {
    padding: 0.5rem 1rem;
    background: #f4f4f4;
    margin: 0.5rem;
  }
  .done {
    text-decoration: line-through;
  }
</style>

<h3>Your todos</h3>
{#if todos}
  {#each todos as todo}
    <div class="todo">
      <p class={todo.completed ? 'done' : ''}>{todo.title}</p>
    </div>
  {/each}
{/if}
