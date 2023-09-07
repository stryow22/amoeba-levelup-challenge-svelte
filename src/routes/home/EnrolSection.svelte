<!-- DeployFeatures.svelte -->
<script>
	import EnrolForm from '$lib/components/Form/EnrolForm.svelte';

	let features = [
		{
			title: 'Take your career to the next level.',
			subtitle: 'With indispensable courses',
			description:
				'Lorem ipsum dolor sit at, consectetur adipielit. Facilisi fermentum, dignissim pharetra. Aliquam Lorem ipsum dolor sit at, consectetur adipielit. Facilisi fermentum, dignissim pharetra. Aliquam Lorem ipsum dolor sit at, consectetur adipielit. Facilisi fermentum, dignissim pharetra. Aliquam.'
		}
	];
</script>

<div class="bg-white py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto max-w-2xl lg:text-center">
			<p class="mt-2 hidden lg:block text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
				Everything you need to deploy your app
			</p>
		</div>
		<dl
			class="mt-16 max-w-2xl sm:mt-20 lg:mt-24 grid grid-cols-1 gap-x-8 gap-y-10 lg:max-w-none lg:grid-cols-2 lg:gap-y-16"
		>
			{#each features as feature}
				<div class="relative hidden lg:block">
					<dt class="text-xl font-semibold leading-7 text-gray-900">
						{feature.title}
					</dt>
					<dt class="text-lg font-semibold leading-7 text-gray-900">
						{feature.subtitle}
					</dt>
					<dd class="mt-2 text-base leading-7 text-gray-600">{feature.description}</dd>
				</div>
			{/each}
			<div class="lg:pl-40 -ml-5 -mt-52 lg:mt-0">
				<EnrolForm />
			</div>
		</dl>
	</div>
</div>

<svg xmlns="http://www.w3.org/2000/svg" class="hidden">
	<symbol
		id="check-circle"
		viewBox="0 0 24 24"
		fill="none"
		stroke-linecap="round"
		stroke-linejoin="round"
		stroke-width="1.5"
	>
		<path d="M22 11.08V12a10 10 0 1 1-5.93-9.14" />
		<path d="M22 4L12 14.01l-3-3" />
	</symbol>
	<symbol
		id="shield"
		viewBox="0 0 24 24"
		fill="none"
		stroke-linecap="round"
		stroke-linejoin="round"
		stroke-width="1.5"
	>
		<path d="M12 22s-8-4.5-8-10V2h16v10c0 5.5-8 10-8 10z" />
	</symbol>
	<symbol
		id="list"
		viewBox="0 0 24 24"
		fill="none"
		stroke-linecap="round"
		stroke-linejoin="round"
		stroke-width="1.5"
	>
		<path d="M8 6h13M8 12h13M8 18h13M3 6h.01M3 12h.01M3 18h.01" />
	</symbol>
	<symbol
		id="lock-closed"
		viewBox="0 0 24 24"
		fill="none"
		stroke-linecap="round"
		stroke-linejoin="round"
		stroke-width="1.5"
	>
		<rect x="3" y="11" width="18" height="11" rx="2" ry="2" />
		<path d="M7 11V7a5 5 0 0 1 9.9-1" />
	</symbol>
</svg>
