<div class="todo done">
	<form action="">
		<input type="hidden" name="done" value="" />
		<button aria-label="Marca completado/no done" class="toggle" />
	</form>

	<form action="" class="text">
		<input type="text" />
		<button aria-label="Guardar Tarea" class="save" />
	</form>

	<form action="">
		<button aria-label="Borrar Tarea" class="delete" />
	</form>
</div>

<style>
	.todo {
		display: grid;
		grid-template-columns: 2rem 1fr 2rem;
		grid-gap: 0.5rem;
		align-items: center;
		margin: 0 0 0.5rem 0;
		padding: 0.5rem;
		background-color: white;
		border-radius: 8px;
		filter: drop-shadow(2px 4px 6px rgba(0, 0, 0, 0.1));
		transform: translate(-1px, -1px);
		transition: filter 0.2s, transform 0.2s;
	}
	.todo button {
		width: 2em;
		height: 2em;
		border: none;
		background-color: transparent;
		background-position: 50% 50%;
		background-repeat: no-repeat;
	}
	.todo input {
		flex: 1;
		padding: 0.5em 2em 0.5em 0.8em;
		border-radius: 3px;
	}
	button.toggle {
		border: 1px solid rgba(0, 0, 0, 0.2);
		border-radius: 50%;
		box-sizing: border-box;
		background-size: 1em auto;
	}
	.text {
		position: relative;
		display: flex;
		align-items: center;
		flex: 1;
	}
	.save {
		position: absolute;
		right: 0;
		opacity: 0;
		background-image: url('https://res.cloudinary.com/daadki0ie/image/upload/v1646874268/save_egh9ed.svg');
	}
	.todo input:focus + .save,
	.save:focus {
		transition: opacity 0.2s;
		opacity: 1;
	}

	.delete {
		background-image: url('https://res.cloudinary.com/daadki0ie/image/upload/v1646874419/delete_n7yvcs.svg');
		opacity: 0.2;
	}

	.delete:hover,
	.delete:focus {
		transition: opacity 0.2s;
		opacity: 1;
	}

	.done {
		transform: none;
		opacity: 0.4;
		filter: drop-shadow(0px 0px 1px rgba(0, 0, 0, 0.1));
	}
	.done .toggle {
		background-image: url('https://res.cloudinary.com/daadki0ie/image/upload/v1646874652/check_nnbpef.svg');
	}
</style>
