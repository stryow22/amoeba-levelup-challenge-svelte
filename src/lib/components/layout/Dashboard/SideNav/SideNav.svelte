<script>
	import logo from '$lib/images/dashboard-logo.png';
</script>

<div
	class="ml-[-100%] fixed z-10 top-0 pb-3 px-6 w-full flex flex-col justify-between h-screen border-r bg-white transition duration-300 md:w-4/12 lg:ml-0 lg:w-[25%] xl:w-[20%] 2xl:w-[15%]"
>
	<div>
		<div class="-mx-6 px-6 py-4">
			<a href="/" title="home">
				<img src={logo} class="w-32" alt="tailus logo" />
			</a>
		</div>

		<ul class="space-y-2 tracking-wide mt-8">
			<li>
				<a
					href="/dashboard"
					aria-label="dashboard"
					class="relative px-4 py-3 flex items-center space-x-4 rounded-xl text-white bg-blue-700"
				>
					<svg class="-ml-1 h-6 w-6" viewBox="0 0 24 24" fill="none">
						<path
							d="M6 8a2 2 0 0 1 2-2h1a2 2 0 0 1 2 2v1a2 2 0 0 1-2 2H8a2 2 0 0 1-2-2V8ZM6 15a2 2 0 0 1 2-2h1a2 2 0 0 1 2 2v1a2 2 0 0 1-2 2H8a2 2 0 0 1-2-2v-1Z"
							class="fill-current text-gray-700"
						/>
						<path
							d="M13 8a2 2 0 0 1 2-2h1a2 2 0 0 1 2 2v1a2 2 0 0 1-2 2h-1a2 2 0 0 1-2-2V8Z"
							class="fill-current text-cyan-200 group-hover:text-cyan-300"
						/>
						<path
							d="M13 15a2 2 0 0 1 2-2h1a2 2 0 0 1 2 2v1a2 2 0 0 1-2 2h-1a2 2 0 0 1-2-2v-1Z"
							class="fill-current group-hover:text-sky-300"
						/>
					</svg>
					<span class="-mr-1 font-medium">Dashboard</span>
				</a>
			</li>
			<li>
				<a
					href="/analytics"
					class="px-4 py-3 flex items-center space-x-4 rounded-md text-gray-600 group"
				>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						viewBox="0 0 20 20"
						fill="currentColor"
					>
						<path
							class="fill-current text-gray-300 group-hover:text-cyan-300"
							fill-rule="evenodd"
							d="M2 6a2 2 0 012-2h4l2 2h4a2 2 0 012 2v1H8a3 3 0 00-3 3v1.5a1.5 1.5 0 01-3 0V6z"
							clip-rule="evenodd"
						/>
						<path
							class="fill-current text-gray-600 group-hover:text-cyan-600"
							d="M6 12a2 2 0 012-2h8a2 2 0 012 2v2a2 2 0 01-2 2H2h2a2 2 0 002-2v-2z"
						/>
					</svg>
					<span class="group-hover:text-gray-700">Analytics</span>
				</a>
			</li>
			<!-- Tambahkan item lainnya sesuai kebutuhan -->
		</ul>
	</div>

	<div class="-mx-6 flex justify-between items-center border-t">
		<img
			src="https://tailus.io/sources/blocks/stats-cards/preview/images/second_user.webp"
			alt=""
			class="w-10 h-10 m-auto rounded-xl object-cover"
		/>
		<div class="text-center">
			<h5 class="hidden mt-4 text-xl font-semibold text-gray-600 lg:block">Easin Arafat</h5>
			<span class="hidden text-gray-400 lg:block">Free Account</span>
		</div>
		<a href="/">
			<button class="px-4 py-3 flex items-center space-x-4 rounded-md text-gray-600 group">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class="h-6 w-6"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M17 16l4-4m0 0l-4-4m4 4H7m6 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h4a3 3 0 013 3v1"
					/>
				</svg>
			</button></a
		>
	</div>
</div>

<style>
	/* Tambahkan gaya CSS Anda di sini */
</style>
