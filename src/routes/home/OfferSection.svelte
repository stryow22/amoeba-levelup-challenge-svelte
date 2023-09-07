<script>
	import Button from '$lib/components/Button/Button.svelte';
	import imageSrc from '$lib/images/hero-2.png';

	let title = 'What we offer';
	let subtitle = 'Online Courses';
	let CTA = 'Our Course are the best among others';
	let description =
		'Lorem ipsum dolor sit at, consectetur adipielit. Facilisi fermentum, dignissim pharetra. Aliquam Lorem ipsum dolor sit at, consectetur adipielit. Facilisi fermentum, dignissim pharetra. Aliquam';
</script>

<div class="bg-white">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<h1 class="text-3xl font-bold tracking-tight text-center text-gray-900 sm:text-4xl">{title}</h1>
		<div class="mt-12 grid gap-16 lg:grid-cols-2 lg:gap-x-5 lg:gap-y-12">
			<div class="mt-10 -mx-4 relative lg:mt-0" aria-hidden="true">
				<img
					class="relative mx-auto max-w-sm lg:max-w-md rounded-lg shadow-lg"
					src={imageSrc}
					alt=""
				/>
			</div>
			<div class="relative">
				<h2 class="text-4xl font-semibold text-slate-600">{subtitle}</h2>
				<h2 class="text-2xl font-semibold text-slate-600">{CTA}</h2>
				<p class="mt-3 mb-10 text-lg text-slate-600">{description}</p>

				<Button variant="outline-sec">Explore our courses</Button>
			</div>
		</div>
	</div>
</div>
