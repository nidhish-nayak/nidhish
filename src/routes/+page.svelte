<script>
	import Hero from '$lib/components/hero.svelte';
	import gsap from 'gsap';
	import { onMount } from 'svelte';

	onMount(() => {
		gsap.from('.loader', {
			width: 0,
			onComplete: function () {
				gsap.to('.loader', { display: 'none' });
				gsap.to('.loading-container', { display: 'none' });
				startBox2Animation();
			}
		});

		gsap.to('.loader', { width: '100%' });
		function startBox2Animation() {
			gsap.to('.hero-page', { y: 200, display: 'block', ease: 'elastic', delay: 1 });
		}
	});
</script>

<div class="loading-container">
	<div class="loader" />
</div>
<div class="hero-page">
	<Hero />
</div>

<style>
	.loading-container {
		width: 75%;
		margin: 0 auto;
		margin-top: 40vh;
	}

	.loader {
		width: 0px;
		height: 10px;
		background-color: red;
	}

	.hero-page {
		display: none;
	}
</style>
