<script>
	import Footer from '$lib/components/layout/Footer/Footer.svelte';
	import Navbar from '../lib/components/layout/Navbar/Navbar.svelte';
	import './styles.css';
</script>

<div class="app">
	<Navbar />

	<main>
		<slot />
	</main>

	<footer>
		<Footer />
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	/* main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	} */

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
