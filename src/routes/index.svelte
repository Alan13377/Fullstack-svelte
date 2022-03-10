<script>
	import TodoSvelte from '../lib/todo-svelte.svelte';
	const title = 'Todos';
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>
<h1>{title}</h1>

<form action="" method="">
	<input type="text" name="text" aria-label="Agregar tarea" placeholder="+ Agregra Tarea" />
</form>

<TodoSvelte />
<TodoSvelte />
<TodoSvelte />
