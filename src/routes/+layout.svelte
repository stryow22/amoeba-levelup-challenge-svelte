<script lang="ts">
	import Footer from '$lib/components/layout/Footer/Footer.svelte';
	import Navbar from '../lib/components/layout/Navbar/Navbar.svelte';
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
	<Navbar />

	<main>
		<slot />
	</main>

	{#if isMobile}
		<div hidden>
			<Footer />
		</div>
	{:else}
		<Footer />
	{/if}
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}
</style>
