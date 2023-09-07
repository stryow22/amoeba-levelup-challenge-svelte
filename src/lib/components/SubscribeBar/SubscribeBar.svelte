<script>
	let emailAddress = '';

	function handleSubmit() {
		console.log('Subscribed with email:', emailAddress);
	}
</script>

<div class="subscribe-container text-center">
	<h2 class="subscribe-heading">Subscribe to get latest updates</h2>

	<div class="mt-6 flex max-w-md">
		<label for="email-address" class="sr-only">Email address</label>
		<input
			bind:value={emailAddress}
			id="email-address"
			name="email"
			type="email"
			autocomplete="email"
			required
			class="subscribe-input"
			placeholder="Enter your email"
		/>
		<button on:click={handleSubmit} class="subscribe-button">Subscribe</button>
	</div>
</div>

<style>
	.subscribe-container {
		max-width: 28rem;
	}

	.subscribe-heading {
		font-size: 1.875rem;
		font-weight: 500;
		letter-spacing: -0.025em;
		color: #fff;
	}

	.subscribe-input {
		min-width: 0;
		flex: 1;
		background-color: rgb(255, 255, 255);
		padding: 0.875rem 1rem;
		color: #fff;
	}

	.subscribe-button {
		flex: none;
		background-color: #3b7586;
		padding: 0.625rem 1rem;
		font-size: 0.875rem;
		font-weight: 600;
		color: #fff;
		cursor: pointer;
		transition: background-color 0.2s ease-in-out;
	}

	.subscribe-button:hover {
		background-color: #2d5a68;
	}
</style>
