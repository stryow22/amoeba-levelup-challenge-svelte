<script lang="ts">
	import { onMount } from 'svelte';

	// Fungsi untuk menghasilkan data acak
	function generateRandomData() {
		const data = [];
		for (let i = 0; i < 10; i++) {
			data.push({
				trackingNo: Math.random().toString(36).substring(7),
				productName: 'Product ' + (i + 1),
				price: (Math.random() * 100).toFixed(2),
				totalOrder: Math.floor(Math.random() * 10) + 1,
				totalAmount: (Math.random() * 1000).toFixed(2)
			});
		}
		return data;
	}

	let recentOrders = generateRandomData();
</script>

<div class="bg-white px-10 py-4 shadow-sm rounded-xl">
	<h1 class="text-2xl font-medium py-4 from-gray-700">Recent Orders</h1>

	<table class="table bg-white rounded-xl shadow-sm">
		<thead>
			<tr>
				<th class="px-4 py-2">Tracking No</th>
				<th class="px-4 py-2">Product Name</th>
				<th class="px-4 py-2">Price</th>
				<th class="px-4 py-2">Total Order</th>
				<th class="px-4 py-2">Total Amount</th>
			</tr>
		</thead>
		<tbody>
			{#each recentOrders as order (order.trackingNo)}
				<tr>
					<td class="px-4 py-2">{order.trackingNo}</td>
					<td class="px-4 py-2">{order.productName}</td>
					<td class="px-4 py-2">${order.price}</td>
					<td class="px-4 py-2">{order.totalOrder}</td>
					<td class="px-4 py-2">${order.totalAmount}</td>
				</tr>
			{/each}
		</tbody>
	</table>
</div>

<style>
	/* Gaya CSS untuk tabel (Tailwind CSS) */
	.table {
		@apply min-w-full divide-y divide-gray-200;
	}

	.table th,
	.table td {
		@apply py-2 px-3 whitespace-nowrap text-left text-sm font-medium text-gray-900;
	}

	.table th {
		@apply bg-gray-100;
	}

	.table tr:hover {
		@apply bg-gray-100;
	}
</style>
