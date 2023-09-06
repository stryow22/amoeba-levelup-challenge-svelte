<script lang="ts">
	import { onMount } from 'svelte';
	import { writable } from 'svelte/store'; // Import store
	import hero from '$lib/images/hero.png';
	import hero2 from '$lib/images/hero-2.png';
	import Button from '../Button/Button.svelte';

	let isMobile: boolean;

	function updateIsMobile() {
		isMobile = window.innerWidth <= 768;
	}

	onMount(() => {
		window.addEventListener('resize', updateIsMobile);
		updateIsMobile();
	});

	// Inisialisasi store untuk melacak indeks gambar
	const currentIndex = writable(0);

	// Daftar gambar yang akan digunakan dalam slider
	const images = [hero, hero2];

	// Fungsi untuk mengganti gambar saat tombol slider diklik
	function changeImage(index: number) {
		currentIndex.set(index);
	}
</script>

<div class="relative isolate overflow-hidden py-24 sm:py-32">
	<img
		src={images[$currentIndex]}
		alt=""
		class="hidden lg:block absolute inset-0 -z-10 h-full w-full object-cover object-right md:object-center"
	/>

	<!-- CTA UTAMA -->
	<div class="absolute inset-0 lg:bg-green-950 opacity-70" />

	<div class="relative mx-auto max-w-7xl px-6 lg:px-8 flex flex-col lg:flex-row">
		<!-- CTA ISI -->
		<div class="lg:w-1/2 lg:order-1 space-y-4">
			<span class="w-96 lg:text-neutral-100 text-6xl font-bold">
				Take your career to<br />the next level.
			</span>
			<p class="w-96 lg:text-neutral-100 text-3xl font-medium tracking-tight">
				With indispensable courses
			</p>

			{#if isMobile}
				<!-- Tombol untuk perangkat mobile -->
				<div class="hidden">
					<Button variant="outline-sec">Exams</Button>
					<Button variant="secondary">Our Courses</Button>
				</div>
			{:else}
				<!-- Tombol untuk desktop -->
				<Button variant="outline">Exams</Button>
				<Button variant="primary">Our Courses</Button>
			{/if}
		</div>

		<div class="lg:w-1/2 lg:order-2">
			<!-- Image Tambahan -->
			<img id="hero" src={images[$currentIndex]} alt="" class="block w-full rounded-3xl my-4" />

			{#if isMobile}
				<p class="pb-4">
					Lorem ipsum dolor sit at, consectetur adipielit. Facilisi fermentum, dignissim pharetra.
					Aliquam Lorem ipsum dolor sit at <a href="/" class="font-bold">Read More...</a>
				</p>

				<!-- Tombol untuk perangkat mobile -->
				<Button variant="outline-sec">Exams</Button>
				<Button variant="secondary">Our Courses</Button>
			{:else}
				<!-- Tombol untuk desktop -->
				<div class="hidden">
					<Button variant="outline">Exams</Button>
					<Button variant="primary">Our Courses</Button>
				</div>
			{/if}
		</div>
	</div>

	<!-- Slider controls -->
	<button
		type="button"
		class="flex absolute top-0 left-0 z-30 justify-center items-center lg:items-end p-8 h-full cursor-pointer group focus:outline-none"
		on:click={() => changeImage(0)}
		data-carousel-prev
	>
		<span
			class="inline-flex justify-center items-center w-8 h-8 rounded-full sm:w-10 sm:h-10 group-focus:outline-none bg-black bg-opacity-60"
		>
			<svg
				class="w-5 h-5 text-white"
				fill="none"
				stroke="currentColor"
				viewBox="0 0 24 24"
				xmlns="http://www.w3.org/2000/svg"
				><path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="1"
					d="M15 19l-7 7 7 7"
				/></svg
			>
			<span class="hidden">Previous</span>
		</span>
	</button>
	<button
		type="button"
		class="flex absolute top-0 right-0 z-30 justify-center items-center lg:items-end p-8 h-full cursor-pointer group focus:outline-none"
		on:click={() => changeImage(1)}
		data-carousel-next
	>
		<span
			class="inline-flex justify-center items-center w-8 h-8 rounded-full sm:w-10 sm:h-10 group-focus:outline-none bg-black bg-opacity-60"
		>
			<svg
				class="w-5 h-5 text-white"
				fill="none"
				stroke="currentColor"
				viewBox="0 0 24 24"
				xmlns="http://www.w3.org/2000/svg"
				><path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M9 5l7 7-7 7"
				/></svg
			>
			<span class="hidden">Next</span>
		</span>
	</button>
</div>
