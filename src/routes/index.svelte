<script context="module" lang="ts">
	import type { Load } from '@sveltejs/kit';
	export const load: Load = async ({ fetch }) => {
		const response = await fetch('/api.json');

		if (response.ok) {
			const todos = await response.json();
			return {
				props: {
					todos
				}
			};
		}
		const { message } = await response.text();
		return {
			error: new Error(message)
		};
	};
</script>

<script lang="ts">
	import '../estilos.css';
	import TodoSvelte from '../lib/todo-svelte.svelte';
	const title = 'Todos';
	export let todos: Todo[];
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

<div class="todos">
	<h1>{title}</h1>

	<form action="/api.json" method="POST" class="new">
		<input type="text" name="text" aria-label="Agregar tarea" placeholder="+ Agregra Tarea" />
	</form>

	{#each todos as todo}
		<TodoSvelte {todo} />
	{/each}
</div>

<style>
	.todos {
		width: 100%;
		max-width: 42rem;
		margin: 4rem auto 0 auto;
	}

	.new {
		margin: 0 0 0.5rem 0;
	}

	.new input {
		font-size: 28px;
		width: 100%;
		padding: 0.5em 1em 0.3em 1em;
		box-sizing: border-box;
		background: rgba(255, 255, 255, 0.5);
		border-radius: 8px;
		text-align: center;
	}

	.todos :global(input) {
		border: 1px solid transparent;
	}

	.todos :global(input:focus-visible) {
		box-shadow: inset 1px 1px 6px rgba(0, 0, 0, 0.1);
		border: 1px solid #ff3300 !important;
		outline: none;
	}
</style>
