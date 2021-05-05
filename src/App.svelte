<script>
	let todos = [{
		content: '吃早饭',
		done: false,
		id: 1
	}, {
		content: '吃午饭',
		done: false,
		id: 2
	}]
	function handleTodoClick({ id }) {
		todos.forEach(todo => {
			if(todo.id === id) todo.done = !todo.done
		})
		todos = todos
	}
</script>

<div class="main">
	{#each todos as todo(todo.id)}
		<div class={todo.done ? "done" : "undo"} on:click={() => handleTodoClick(todo)}>{todo.content}</div>
	{/each}
	
</div>

<style>
	.done {
		color: gray
	}
	.undo {
		color: black
	}
</style>