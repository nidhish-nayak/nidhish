<script>
	import gsap from 'gsap';
	import { onMount } from 'svelte';

	onMount(() => {
		gsap.from('.box', { x: -300, duration: 0.5 });
	});
</script>

<h1 class="box">Hey there</h1>
