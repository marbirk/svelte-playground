<script lang="ts">
	import { onMount, beforeUpdate, afterUpdate, onDestroy } from 'svelte';

	onMount(() => {
		console.log('the component has mounted');
	});

	beforeUpdate(() => {
		console.log('the component is about to update');
	});

	afterUpdate(() => {
		console.log('the component just updated');
	});

	onDestroy(() => {
		console.log('the component is being destroyed');
	});

	export let name: string;
	let count: number = 0;

	function handleClick():void {
		count += 1;
	}
	function reset():void {
		count = 0;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<h2>Svelte is:</h2>
	<iframe src="https://giphy.com/embed/JUqiFbumTAPYIeM8yJ" width="480" height="480" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/reaction-cool-nice-JUqiFbumTAPYIeM8yJ">via GIPHY</a></p>
	<button on:click={handleClick}>
		Clicked {count} {count === 1 ? 'time' : 'times'}
	</button>
	<button on:click={reset}>
		Reset
	</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: blue;
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