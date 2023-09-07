<script src="https://cdnjs.cloudflare.com/ajax/libs/flowbite/1.8.1/datepicker.min.js">
	// @ts-nocheck

	import Card from './Card.svelte';
	import Chart from './Chart.svelte';
	import Product from './Product.svelte';
	import Tabel from './Tabel.svelte';
</script>

<div class="ml-auto mb-6 lg:w-[75%] xl:w-[80%] 2xl:w-[85%] bg-gray-50">
	<div class="sticky z-10 top-0 h-16 lg:py-2.5">
		<div class="px-6 flex items-center justify-between space-x-4 2xl:container">
			<h5 hidden class="text-2xl text-gray-600 font-medium lg:block">Dashboard</h5>
			<div class="flex space-x-4">
				<div date-rangepicker class="flex items-center">
					<div class="relative">
						<div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
							<svg
								class="w-4 h-4 text-gray-500"
								aria-hidden="true"
								xmlns="http://www.w3.org/2000/svg"
								fill="currentColor"
								viewBox="0 0 20 20"
							>
								<path
									d="M20 4a2 2 0 0 0-2-2h-2V1a1 1 0 0 0-2 0v1h-3V1a1 1 0 0 0-2 0v1H6V1a1 1 0 0 0-2 0v1H2a2 2 0 0 0-2 2v2h20V4ZM0 18a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V8H0v10Zm5-8h10a1 1 0 0 1 0 2H5a1 1 0 0 1 0-2Z"
								/>
							</svg>
						</div>
						<input
							name="start"
							type="text"
							class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5"
							placeholder="Select date start"
						/>
					</div>
					<span class="mx-4 text-gray-500">to</span>
					<div class="relative">
						<div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
							<svg
								class="w-4 h-4 text-gray-500"
								aria-hidden="true"
								xmlns="http://www.w3.org/2000/svg"
								fill="currentColor"
								viewBox="0 0 20 20"
							>
								<path
									d="M20 4a2 2 0 0 0-2-2h-2V1a1 1 0 0 0-2 0v1h-3V1a1 1 0 0 0-2 0v1H6V1a1 1 0 0 0-2 0v1H2a2 2 0 0 0-2 2v2h20V4ZM0 18a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V8H0v10Zm5-8h10a1 1 0 0 1 0 2H5a1 1 0 0 1 0-2Z"
								/>
							</svg>
						</div>
						<input
							name="end"
							type="text"
							class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5"
							placeholder="Select date end"
						/>
					</div>
				</div>
			</div>
		</div>
	</div>

	<div class="px-6 pt-6">
		<div class="grid gap-6 lg:grid-cols-2">
			<div class="md:col-span-2 lg:col-span-1">
				<!-- Data Atas -->
				<div class="mb-8">
					<Card />
				</div>

				<!-- Chart -->
				<div class="mb-8">
					<Chart />
				</div>
			</div>
		</div>

		<!-- Product -->
		<div class="mb-8">
			<Product />
		</div>
	</div>
</div>
