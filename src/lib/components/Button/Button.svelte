<!-- Button.svelte -->
<script>
	export let variant = 'primary';
</script>

<button class={`button button-${variant}`}>
	<slot />
</button>

<style>
	.button {
		padding-left: 50px;
		padding-right: 50px;
		padding-top: 12px;
		padding-bottom: 12px;
		border-radius: 5px;
	}

	.button-primary {
		background: white;
		color: #1b353d;
	}

	.button-outline {
		border: 0.5px white solid;
		background: transparent;
		color: white;
	}

	.button-outline-sec {
		border: 0.5px #1b353d solid;
		background: transparent;
		color: #1b353d;
	}

	.button-secondary {
		background: #1b353d;
		color: white;
	}
</style>
