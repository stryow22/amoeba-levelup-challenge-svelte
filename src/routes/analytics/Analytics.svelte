<script lang="ts">
	import Button from '$lib/components/Button/Button.svelte';
	import Chart from 'chart.js/auto';

	import { onMount, afterUpdate } from 'svelte';

	let barChart: Chart<'bar', number[], string>;
	let donutChart: Chart<'doughnut', number[], string>;

	// Data untuk chart bar
	const barChartData = {
		labels: ['Label 1', 'Label 2', 'Label 3', 'Label 4', 'Label 5'],
		datasets: [
			{
				label: 'Data Bar Chart',
				data: [10, 20, 30, 40, 50],
				backgroundColor: 'rgba(75, 192, 192, 0.2)',
				borderColor: 'rgba(75, 192, 192, 1)',
				borderWidth: 1
			}
		]
	};

	// Data untuk chart donut
	const donutChartData = {
		labels: ['Label 1', 'Label 2', 'Label 3'],
		datasets: [
			{
				data: [30, 40, 30],
				backgroundColor: [
					'rgba(255, 99, 132, 0.2)',
					'rgba(54, 162, 235, 0.2)',
					'rgba(255, 206, 86, 0.2)'
				],
				borderColor: ['rgba(255, 99, 132, 1)', 'rgba(54, 162, 235, 1)', 'rgba(255, 206, 86, 1)'],
				borderWidth: 1
			}
		]
	};

	// Fungsi untuk menginisialisasi dan menggambar chart
	function initializeCharts() {
		// Inisialisasi chart bar
		const barChartCanvas = document.getElementById('barChart') as HTMLCanvasElement;
		barChart = new Chart(barChartCanvas, {
			type: 'bar',
			data: barChartData,
			options: {
				scales: {
					y: {
						beginAtZero: true
					}
				}
			}
		});

		// Inisialisasi chart donut
		const donutChartCanvas = document.getElementById('donutChart') as HTMLCanvasElement;
		donutChart = new Chart(donutChartCanvas, {
			type: 'doughnut',
			data: donutChartData
		});
	}

	onMount(() => {
		initializeCharts();
	});

	afterUpdate(() => {
		// Update chart jika ada perubahan data
		barChart.data = barChartData;
		barChart.update();

		donutChart.data = donutChartData;
		donutChart.update();
	});

	// Fungsi untuk menghasilkan data acak untuk pelanggan
	function generateRandomCustomers() {
		const customers = [];
		const genders = ['male', 'female'];
		for (let i = 0; i < 20; i++) {
			const gender = genders[Math.floor(Math.random() * genders.length)];
			customers.push({
				name: 'Customer ' + (i + 1),
				email: 'customer' + (i + 1) + '@example.com',
				phone: '123-456-789' + i,
				gender: gender
			});
		}
		return customers;
	}

	let customerList = generateRandomCustomers();
	let selectedCustomer: { name: any; email: any; phone: any; gender: any } | null = null;

	// Fungsi untuk menampilkan detail pelanggan di sidebar
	function showCustomerDetail(customer: {
		name: string;
		email: string;
		phone: string;
		gender: string;
	}) {
		selectedCustomer = customer;
	}

	let isSidebarOpen = false;

	// Data untuk form registrasi
	let registrationData = {
		image: '',
		firstName: '',
		lastName: '',
		email: '',
		phone: '',
		gender: 'male' // Default gender: male
	};

	// Fungsi untuk membuka sidebar dengan form register
	function openSidebar() {
		isSidebarOpen = true;
	}

	// Fungsi untuk menutup sidebar
	function closeSidebar() {
		isSidebarOpen = false;
	}

	// Fungsi untuk menyimpan data registrasi
	function saveRegistration() {
		// Proses penyimpanan data registrasi di sini
		// Anda dapat mengakses data registrasi melalui variabel registrationData
		console.log(registrationData);
		// Setelah proses penyimpanan selesai, tutup sidebar
		closeSidebar();
	}
</script>

<div class="bg-gray-50 ml-auto mb-6 lg:w-[75%] xl:w-[80%] 2xl:w-[85%]">
	<div class="top-0 h-16 lg:py-2.5">
		<div class="px-6 flex items-center justify-between space-x-4 2xl:container">
			<h5 hidden class="text-2xl text-gray-600 font-medium lg:block">Customer List</h5>
			<div class="bg-blue-700 rounded-lg">
				<a on:click={openSidebar}><Button variant="outline">+ Add Customer</Button></a>
			</div>
		</div>
	</div>

	<div class="px-6 pt-6 2xl:container">
		<div class="grid lg:grid-cols-1">
			<div class="flow-root">
				<table class="min-w-full border-collapse">
					<thead>
						<tr>
							<th class="py-2 px-3">Name</th>
							<th class="py-2 px-3">Email</th>
							<th class="py-2 px-3">Phone Number</th>
							<th class="py-2 px-3">Gender</th>
							<th class="py-2 px-3">Action</th>
						</tr>
					</thead>
					<tbody>
						{#each customerList as customer (customer.name)}
							<tr
								on:click={() => showCustomerDetail(customer)}
								class="cursor-pointer hover:bg-gray-100"
							>
								<td class="py-4 px-4 flex items-center">
									<img
										src={`https://via.placeholder.com/24x24?text=${customer.name.charAt(0)}`}
										alt={customer.name}
										class="w-6 h-6 rounded-full mr-2"
									/>
									{customer.name}
								</td>
								<td class="py-2 px-3">{customer.email}</td>
								<td class="py-2 px-3">{customer.phone}</td>
								<td class="py-2 px-3">
									<span class="gender-badge gender-{customer.gender}">
										{customer.gender}
									</span>
								</td>
								<td class="py-2 px-3">
									<button class="text-blue-500 hover:underline mr-2">Edit</button>
									<button class="text-red-500 hover:underline">Delete</button>
								</td>
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
		</div>
	</div>
</div>

<div
	class="fixed top-0 right-0 h-full w-1/4 bg-white overflow-y-auto"
	class:hidden={!selectedCustomer}
	style="display: {selectedCustomer ? 'block' : 'none'}"
>
	<div class="p-6">
		{#if selectedCustomer}
			<div class="border-b text-center mx-auto mb-4">
				<img
					src={`https://via.placeholder.com/24x24?text=${selectedCustomer.name.charAt(0)}`}
					class="w-40 rounded-full mx-auto"
					alt=""
				/>
				<h2 class="text-xl font-semibold mb-4">{selectedCustomer.name}</h2>
			</div>
			<div class="mb-2">
				<strong>Email:</strong>
				{selectedCustomer.email}
			</div>
			<div class="mb-2">
				<strong>Phone Number:</strong>
				{selectedCustomer.phone}
			</div>
			<div>
				<strong>Gender:</strong>
				<span class="gender-badge gender-{selectedCustomer.gender}">
					{selectedCustomer.gender}
				</span>
			</div>
		{/if}

		<!-- chart Bar: Performance -->
		<div class="mb-8">
			<canvas id="barChart" width="400" height="200" />
		</div>

		<!-- chart donut -->
		<div class="mb-8">
			<canvas id="donutChart" width="400" height="200" />
		</div>
	</div>
</div>

<div
	class="fixed top-0 right-0 h-full w-[25%] bg-white overflow-y-auto"
	class:hidden={!isSidebarOpen}
	style="display: {isSidebarOpen ? 'block' : 'none'}"
>
	<div class="p-6">
		<!-- Form register di sini -->
		<h2 class="text-xl font-semibold mb-4">Add Customer</h2>
		<form>
			<!-- Input gambar -->
			<div class="mb-4">
				<label for="image" class="block text-gray-600">Image</label>
				<input
					type="file"
					id="image"
					name="image"
					accept="image/*"
					bind:value={registrationData.image}
				/>
			</div>

			<!-- Input first name -->
			<div class="mb-4">
				<label for="firstName" class="block text-gray-600">First Name</label>
				<input
					type="text"
					id="firstName"
					name="firstName"
					bind:value={registrationData.firstName}
				/>
			</div>

			<!-- Input last name -->
			<div class="mb-4">
				<label for="lastName" class="block text-gray-600">Last Name</label>
				<input type="text" id="lastName" name="lastName" bind:value={registrationData.lastName} />
			</div>

			<!-- Input email -->
			<div class="mb-4">
				<label for="email" class="block text-gray-600">Email</label>
				<input type="email" id="email" name="email" bind:value={registrationData.email} />
			</div>

			<!-- Input phone -->
			<div class="mb-4">
				<label for="phone" class="block text-gray-600">Phone</label>
				<input type="text" id="phone" name="phone" bind:value={registrationData.phone} />
			</div>

			<!-- Dropdown gender -->
			<div class="mb-4">
				<label class="block text-gray-600">Gender</label>
				<select id="gender" name="gender" bind:value={registrationData.gender}>
					<option value="male">Male</option>
					<option value="female">Female</option>
				</select>
			</div>

			<div class="mt-4">
				<!-- svelte-ignore a11y-invalid-attribute -->
				<a href="" on:click={saveRegistration}>
					<Button variant="secondary">Add Customer</Button></a
				>
			</div>
		</form>
	</div>
</div>

<style>
	/* Gaya CSS untuk badge gender */
	.gender-badge {
		@apply inline-block px-2 py-1 rounded-full text-white text-xs;
	}

	.gender-male {
		@apply bg-blue-500;
	}

	.gender-female {
		@apply bg-red-500;
	}
</style>
