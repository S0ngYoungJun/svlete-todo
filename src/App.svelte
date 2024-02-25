<script>
  let todos = [];
  let newTodo = '';

  function addTodo() {
    if (newTodo.trim() === '') return;
    todos.push(newTodo);
    newTodo = ''; // 입력 필드 초기화
  }
</script>


<main>
  <input bind:value={newTodo} on:keyup="{e => (e.key === 'Enter' && addTodo())}" placeholder="할 일을 입력하세요">
  <button on:click="{addTodo}">추가</button>

  <ul>
    {#each todos as todo}
      <li>{todo}</li>
    {/each}
  </ul>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
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