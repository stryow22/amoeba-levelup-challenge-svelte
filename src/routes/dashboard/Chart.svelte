<script>
	import { onMount } from 'svelte';
	import Chart from 'chart.js/auto';

	let lineChart;
	let donutChart;

	// Fungsi untuk menghasilkan data acak
	function generateRandomData() {
		const data = [];
		for (let i = 0; i < 7; i++) {
			data.push(Math.floor(Math.random() * 100));
		}
		return data;
	}

	// Data x (jam)
	const labels = ['11am', '12pm', '1pm', '2pm', '3pm', '4pm', '5pm', '6pm', '7pm'];

	// Data y (0 - 100)
	// @ts-ignore
	// @ts-ignore
	const dataY = [0, 20, 40, 60, 80, 100, 80, 60, 40];

	// Konfigurasi chart pertama (line chart)
	const lineChartData = {
		labels: labels,
		datasets: [
			{
				label: 'Reports',
				data: generateRandomData(),
				fill: false,
				borderColor: '#5B93FF',
				borderWidth: 3
			}
		]
	};

	// Konfigurasi chart kedua (donut chart)
	const donutChartData = {
		labels: ['Sales', 'Distribute', 'Return'],
		datasets: [
			{
				data: [30, 30, 40],
				backgroundColor: ['#FFD700', '#32CD32', '#FF4500']
			}
		]
	};

	// Membuat chart setelah komponen dimuat
	onMount(() => {
		// Membuat chart pertama (line chart)
		// @ts-ignore
		const lineCtx = document.getElementById('lineChart').getContext('2d');
		lineChart = new Chart(lineCtx, {
			type: 'line', // Mengubah tipe chart menjadi line chart
			data: lineChartData,
			options: {
				scales: {
					x: {
						title: {
							display: false,
							text: 'X'
						}
					},
					y: {
						title: {
							display: false,
							text: 'Y'
						}
					}
				}
			}
		});

		// Membuat chart kedua (donut chart)
		// @ts-ignore
		const donutCtx = document.getElementById('donutChart').getContext('2d');
		donutChart = new Chart(donutCtx, {
			type: 'doughnut', // Menggunakan tipe chart doughnut
			data: donutChartData,
			options: {
				responsive: true,
				maintainAspectRatio: false
			}
		});
	});
</script>

<!-- Menampilkan chart menggunakan elemen canvas -->
<div class="flex flex-row gap-4">
	<canvas
		id="lineChart"
		class="flex-1 h-[70vh] w-[70vw] lg:h-[70vh] lg:w-[70vw] rounded-xl shadow-sm"
		style="background-color: white;"
	/>
	<canvas
		id="donutChart"
		class="flex-1 h-[30vh] w-[30vw] lg:h-[30vh] lg:w-[30vw] rounded-xl shadow-sm"
		style="background-color: white;"
	/>
</div>
