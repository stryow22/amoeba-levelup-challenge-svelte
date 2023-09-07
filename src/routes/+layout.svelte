<script lang="ts">
	import { onMount } from 'svelte';
	import './styles.css';

	let isMobile: boolean;

	function updateIsMobile() {
		isMobile = window.innerWidth <= 768;
	}

	onMount(() => {
		window.addEventListener('resize', updateIsMobile);
		updateIsMobile();
	});
</script>

<div class="app">
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
</style>
