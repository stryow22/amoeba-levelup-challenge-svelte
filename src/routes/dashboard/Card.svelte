<script>
	// Import your card image
	import cardImg1 from '$lib/images/card1.png';

	// Define card data
	let cardData = [
		{ value: '178+', label: 'Save Product' },
		{ value: '20+', label: 'Stock Product' },
		{ value: '120+', label: 'Sales Product' },
		{ value: '12', label: 'Job Application' }
	];
</script>

<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 lg:gap-80 gap-y-6">
	{#each cardData as card, index}
		<div class="h-full w-72 py-8 px-6 space-y-6 rounded-xl shadow-sm bg-white">
			<div class="flex">
				<div class="flex-shrink-0">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="w-20 h-20 text-gray-700"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M12 6v6m0 0v6m0-6h6m-6 0H6"
						/>
					</svg>
				</div>
				<div class="ml-4">
					<div class="mt-2 flex gap-4">
						<h3 class="text-3xl font-bold text-gray-700">{card.value}</h3>
					</div>
					<span class="block text-gray-500">{card.label}</span>
				</div>
			</div>
		</div>
	{/each}
</div>
