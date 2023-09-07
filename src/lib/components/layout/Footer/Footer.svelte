<script>
	import fbIcon from '$lib/images/icon/fb.svg';
	import igIcon from '$lib/images/icon/ig.svg';
	import inIcon from '$lib/images/icon/in.svg';
	import twIcon from '$lib/images/icon/tw.svg';
	import logo2 from '$lib/images/logo-2.png';
	import brand from '$lib/images/brand.png';
	import SubscribeBar from '$lib/components/SubscribeBar/SubscribeBar.svelte';
</script>

<footer class="bg-slate-700">
	<div class="max-w-screen-xl px-4 py-16 mx-auto sm:px-6 lg:px-8">
		<div class="grid grid-cols-1 gap-8 lg:grid-cols-2">
			<div>
				<img src={logo2} class="mr-5 h-6 sm:h-9" alt="logo" />
				<p class="max-w-xs mt-4 text-sm text-white">
					We are not here to sell you products, we sell value through our expertise.
				</p>
				<div class="flex mt-8 space-x-6 text-white">
					<a class="hover:opacity-75" href="/" target="_blank" rel="noreferrer">
						<img src={fbIcon} alt="Facebook" />
					</a>
					<a class="hover:opacity-75" href="/" target="_blank" rel="noreferrer">
						<img src={igIcon} alt="Facebook" />
					</a>
					<a class="hover:opacity-75" href="/" target="_blank" rel="noreferrer">
						<img src={inIcon} alt="Facebook" />
					</a>
					<a class="hover:opacity-75" href="/" target="_blank" rel="noreferrer">
						<img src={twIcon} alt="Facebook" />
					</a>
				</div>
			</div>

			<div class="grid grid-cols-1 gap-8 lg:col-span-1 sm:grid-cols-2 lg:grid-cols-2">
				<div>
					<p class="font-medium text-white">Address:</p>
					<nav class="flex flex-col mb-2 space-y-2 text-sm text-white">
						<p>38 opebi Road, Ikeja, Lagos State, Nigeia.</p>
					</nav>

					<p class="font-medium text-white">Phone:</p>
					<nav class="flex flex-col mb-2 space-y-2 text-sm text-white">
						<p>+2349022396389</p>
					</nav>

					<p class="font-medium text-white">Email:</p>
					<nav class="flex flex-col mb-2 space-y-2 text-sm text-white">
						<p>contact@contentionary.com</p>
					</nav>
				</div>

				<div>
					<p class="font-medium text-white">Company</p>
					<nav class="flex flex-col mt-4 space-y-2 text-sm text-white">
						<a class="hover:opacity-75" href="/"> About Us </a>
						<a class="hover:opacity-75" href="/"> Features </a>
						<a class="hover:opacity-75" href="/"> Pricing </a>
					</nav>
				</div>
			</div>
		</div>

		<div class="my-10 mx-auto max-w-lg">
			<SubscribeBar />
		</div>

		<img class="mt-20" src={brand} alt="logoo" />
	</div>
</footer>
