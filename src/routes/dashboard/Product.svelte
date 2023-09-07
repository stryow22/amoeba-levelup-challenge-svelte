<script lang="ts">
	import { onMount } from 'svelte';
	import Tabel from './Tabel.svelte';

	// Fungsi untuk menghasilkan data acak untuk produk
	function generateRandomProduct() {
		const products = [];
		for (let i = 0; i < 2; i++) {
			products.push({
				name: 'Product ' + (i + 1),
				rating: Math.floor(Math.random() * 5) + 1,
				price: (Math.random() * 100).toFixed(2),
				imageUrl: 'https://via.placeholder.com/150' // Ganti URL gambar dengan yang sesuai
			});
		}
		return products;
	}

	let topSellingProducts = generateRandomProduct();
</script>

<div class="flex flex-row gap-4">
	<Tabel />

	<div class="bg-white rounded-xl shadow-sm px-2">
		<h1 class="text-2xl font-semibold p-4">Top Selling</h1>
		{#each topSellingProducts as product (product.name)}
			<div class="product-card">
				<img class="product-image" src={product.imageUrl} alt={product.name} />
				<div class="product-details">
					<div class="product-title">{product.name}</div>
					<div class="product-rating">
						{#each Array(product.rating) as _, i}
							<svg class="star-icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
								<path
									d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm-2-6h4v-2h-4zm0-4h4V7h-4z"
								/>
							</svg>
						{/each}
					</div>
					<div class="product-price">${product.price}</div>
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.product-card {
		@apply flex items-center p-4 bg-white rounded-xl shadow-sm mb-4;
	}

	.product-image {
		@apply w-1/4 mr-4 rounded-xl;
	}

	.product-details {
		@apply w-3/4;
	}

	.product-title {
		@apply text-lg font-semibold mb-2;
	}

	.product-rating {
		@apply flex items-center text-yellow-500 mb-2;
	}

	.product-price {
		@apply text-gray-600;
	}

	.star-icon {
		@apply w-4 h-4 fill-current mr-1;
	}
</style>
