<!-- Footer.svelte -->
<script>
	import fbIcon from '$lib/images/icon/fb.svg';
	import igIcon from '$lib/images/icon/ig.svg';
	import inIcon from '$lib/images/icon/in.svg';
	import twIcon from '$lib/images/icon/tw.svg';
	import logo from '$lib/images/logo.png';
</script>

<footer class="bg-slate-700">
	<div class="max-w-screen-xl px-4 py-16 mx-auto sm:px-6 lg:px-8">
		<div class="grid grid-cols-1 gap-8 lg:grid-cols-3">
			<div>
				<img src={logo} class="mr-5 h-6 sm:h-9" alt="logo" />
				<p class="max-w-xs mt-4 text-sm text-gray-600">
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptas, accusantium.
				</p>
				<div class="flex mt-8 space-x-6 text-gray-600">
					<a class="hover:opacity-75" href="/" target="_blank" rel="noreferrer">
						<span class="sr-only"> Facebook </span>
						<img src={fbIcon} alt="Facebook" />
					</a>
					<a class="hover:opacity-75" href="/" target="_blank" rel="noreferrer">
						<span class="sr-only"> Facebook </span>
						<img src={igIcon} alt="Facebook" />
					</a>
					<a class="hover:opacity-75" href="/" target="_blank" rel="noreferrer">
						<span class="sr-only"> Facebook </span>
						<img src={inIcon} alt="Facebook" />
					</a>
					<a class="hover:opacity-75" href="/" target="_blank" rel="noreferrer">
						<span class="sr-only"> Facebook </span>
						<img src={twIcon} alt="Facebook" />
					</a>
				</div>
			</div>
			<div class="grid grid-cols-1 gap-8 lg:col-span-2 sm:grid-cols-2 lg:grid-cols-4">
				<div>
					<p class="font-medium">Company</p>
					<nav class="flex flex-col mt-4 space-y-2 text-sm text-gray-500">
						<a class="hover:opacity-75" href="/"> About </a>
						<a class="hover:opacity-75" href="/"> Meet the Team </a>
					</nav>
				</div>
				<div>
					<p class="font-medium">Services</p>
					<nav class="flex flex-col mt-4 space-y-2 text-sm text-gray-500">
						<a class="hover:opacity-75" href="/"> 1on1 Coaching </a>
						<a class="hover:opacity-75" href="/"> Company Review </a>
					</nav>
				</div>
			</div>
		</div>
		<p class="mt-8 text-xs text-gray-800">© 2022 Company Name</p>
	</div>
</footer>
