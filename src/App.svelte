<script>
  import Navbar from './Navbar.svelte';
  import Todos from './Todos.svelte';
  import AddTodo from './AddTodo.svelte';

  let todos = null;

  async function getTodos() {
    const res = await fetch('https://jsonplaceholder.typicode.com/todos');

    const json = await res.json();

    console.log(json);
    todos = json;
  }

  async function addTodo(title) {
    const res = await fetch('https://jsonplaceholder.typicode.com/todos', {
      method: 'POST',
      body: JSON.stringify({
        title: title,
        userId: 2,
        completed: false,
      }),
      headers: {
        'Content-type': 'application/json',
      },
    });

    let todo = await res.json();

    todos.unshift(todo);

    todos = todos;

    console.log(todos);
  }
</script>

<style>
  .container {
    width: 80%;
    margin: 0 auto;
    display: grid;
  }
</style>

<main>
  <Navbar />
  <div class="container">
    <AddTodo {addTodo} />
    <Todos {getTodos} {todos} />
  </div>
</main>
