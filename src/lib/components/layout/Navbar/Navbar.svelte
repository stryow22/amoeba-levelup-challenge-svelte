<script>
	import { page } from '$app/stores';
	import SearchBar from '$lib/components/SearchBar/SearchBar.svelte';
	import logo from '$lib/images/logo.png';
	import userAccount from '$lib/images/user.png';

	let mobileMenuOpen = false;

	function toggleMobileMenu() {
		mobileMenuOpen = !mobileMenuOpen;
	}
</script>

<header class="bg-white shadow-sm">
	<div class="container mx-auto px-4 py-4 flex items-center justify-between">
		<!-- Mobile Burger btn -->
		<button
			class="lg:hidden block text-gray-600 hover:text-gray-800 focus:outline-none"
			on:click={toggleMobileMenu}
		>
			<svg
				class="w-6 h-6"
				fill="none"
				stroke="currentColor"
				viewBox="0 0 24 24"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 6h16M4 12h16M4 18h16"
				/>
			</svg>
		</button>

		<div>
			<a href="/">
				<img src={logo} alt="SvelteKit" />
			</a>
		</div>

		<!-- Nav Menu -->
		<nav class="hidden lg:flex">
			<ul class="flex gap-4">
				<li class="relative" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
					<a href="/" class="text-gray-700 hover:text-gray-900"> Home </a>
				</li>
				<li class="relative" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
					<a href="/" class="text-gray-700 hover:text-gray-900"> Courses </a>
				</li>
				<li class="relative" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
					<a href="/" class="text-gray-700 hover:text-gray-900"> Instructors </a>
				</li>
				<li class="relative" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
					<a href="/" class="text-gray-700 hover:text-gray-900"> Schedules </a>
				</li>
				<li class="relative" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
					<a href="/" class="text-gray-700 hover:text-gray-900"> Contact Us </a>
				</li>
			</ul>
		</nav>

		<!-- Search Bar -->
		<SearchBar />

		<div>
			<a href="/">
				<img src={userAccount} alt="userAccount" />
			</a>
		</div>
	</div>

	<!-- Mobile Menu -->
	<div class={`lg:hidden ${mobileMenuOpen ? 'block' : 'hidden'} bg-white border-t border-gray-200`}>
		<ul class="px-4 py-2">
			<li class="mb-2" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/" class="text-gray-700 hover:text-gray-900"> Home </a>
			</li>
			<li class="mb-2" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/" class="text-gray-700 hover:text-gray-900"> Courses </a>
			</li>
			<li class="mb-2" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/" class="text-gray-700 hover:text-gray-900"> Instructors </a>
			</li>
			<li class="mb-2" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/" class="text-gray-700 hover:text-gray-900"> Schedules </a>
			</li>
			<li class="mb-2" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/" class="text-gray-700 hover:text-gray-900"> Contact Us </a>
			</li>
		</ul>
	</div>
</header>
