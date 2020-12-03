<script>
	import { onMount } from 'svelte';
	import Button from "./Button.svelte";
	import Card from "./Card.svelte";
	import Input from './Input.svelte'
	import { highlightedName } from './stores.js'
	$: users = [];

	onMount(async () => {
		await getData();
	});

	async function getData() {
		const data = await fetch("https://jsonplaceholder.typicode.com/users?_limit=" + Math.floor(Math.random() * Math.floor(10)));
		users = await data.json();
	}
</script>

<main>
	<div class='cards'>
		{#each users as user (user.id)}
	<Card entry={user} passedName={$highlightedName}></Card>
	{/each}
	</div>
	<Button text="Refresh" clickHandler="{() => {getData()}}" />
	<Input/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}

	.cards {
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		flex-wrap: wrap;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>