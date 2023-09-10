<script>
	import Loading from '$lib/Loading.svelte';
	import { onMount } from 'svelte';
	import '../app.scss';

	let showComponent = true;
	onMount(() => {
		setTimeout(() => {
			showComponent = false;
		}, 5000);
	});
</script>

{#if showComponent}
	<Loading />
{/if}

{#if !showComponent}
	<nav>
		<div class="logo">
			<img src="/Logo.svg" alt="my-logo" />
		</div>
		<ul>
			<li><a href="/">Home</a></li>
			<li><a href="/projects">Projects</a></li>
			<li><a href="/about">About</a></li>
		</ul>
	</nav>
	<slot />
{/if}

<style lang="scss">
	.logo {
		margin: 1em;
	}

	nav {
		display: flex;
		justify-content: space-between;
	}

	ul {
		display: flex;
		margin-right: 2em;
	}

	li {
		list-style: none;
	}

	a {
		font-family: sans-serif;
		text-decoration: none;
		color: black;
		padding: 1.5em;
	}

	a:hover {
		background-color: lightblue;
	}
</style>
