<script>
	let people = [
		{
			name: 'Prof. W.J Khatam',
			role: 'Data Analyst',
			image: 'https://randomuser.me/api/portraits/men/1.jpg'
		},
		{
			name: 'Prof. Kaif Kofi O',
			role: 'UX Designer',
			image: 'https://randomuser.me/api/portraits/women/2.jpg'
		},
		{
			name: 'Prof. Maryam J',
			role: 'Software Dev.',
			image: 'https://randomuser.me/api/portraits/men/3.jpg'
		},
		{
			name: 'Mr. Oluwole B.O',
			role: 'Pysicologist',
			image: 'https://randomuser.me/api/portraits/men/4.jpg'
		}
	];
</script>

<div class="bg-white py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto max-w-2xl text-center">
			<h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
				Notable Intructors
			</h2>
		</div>
		<div class="mx-auto mt-16 max-w-2xl sm:mt-20 lg:mt-24 lg:max-w-6xl">
			<ul role="list" class="flex flex-wrap justify-center gap-x-8 gap-y-12 sm:gap-y-16">
				{#each people as person}
					<li>
						<div class="flex flex-col items-center gap-y-6 lg:px-10 text-center">
							<img class="h-24 w-24 rounded-full" src={person.image} alt={person.name} />
							<div>
								<p class="text-sm font-semibold leading-6 text-slate-600">{person.role}</p>
								<h3 class="text-lg font-semibold leading-7 tracking-tight text-gray-900">
									{person.name}
								</h3>
							</div>
						</div>
					</li>
				{/each}
			</ul>
		</div>
	</div>
</div>
