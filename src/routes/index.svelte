<script>
	import { pokemon } from '../stores/pokestore';
	console.log($pokemon);
</script>

<svelte:head>
	<title>SvelteKit Pokedex</title>
</svelte:head>

<h1>SvelteKit Pokedex</h1>

{#each $pokemon as pokeman}
	<p>{pokeman.name}</p>
{/each}
