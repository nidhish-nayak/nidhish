<script>
</script>

<div class="app">
	<header>
		<div />
		<nav />
	</header>

	<main>
		<slot />
	</main>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
	}
</style>
