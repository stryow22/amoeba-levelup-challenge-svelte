<!-- RegistrationForm.svelte -->

<script>
	import Button from '../Button/Button.svelte';

	let fullName = '';
	let email = '';
	let phoneNumber = '';
	let selectedCourse = '';

	function handleSubmit() {
		console.log('Full Name:', fullName);
		console.log('Email:', email);
		console.log('Phone Number:', phoneNumber);
		console.log('Selected Course:', selectedCourse);
	}
</script>

<div class="w-96 relative bg-white rounded-lg lg:shadow">
	<form on:submit={handleSubmit}>
		<div class="p-4">
			<div class="text-zinc-800 text-2xl font-semibold leading-snug mb-6">
				Registration for enrolment
			</div>

			<div class="mb-4">
				<label class="text-stone-500 text-base font-normal leading-snug">Full name</label>
				<input
					type="text"
					bind:value={fullName}
					class="w-full h-10 bg-gray-50 rounded-md border border-gray-300 px-4"
					placeholder="Enter your full name"
					required
				/>
			</div>

			<div class="mb-4">
				<label class="text-stone-500 text-base font-normal leading-snug">Email</label>
				<input
					type="email"
					bind:value={email}
					class="w-full h-10 bg-gray-50 rounded-md border border-gray-300 px-4"
					placeholder="Enter your email"
					required
				/>
			</div>

			<div class="mb-4">
				<label class="text-stone-500 text-base font-normal leading-snug">Phone number</label>
				<input
					type="tel"
					bind:value={phoneNumber}
					class="w-full h-10 bg-gray-50 rounded-md border border-gray-300 px-4"
					placeholder="Enter your phone number"
					required
				/>
			</div>

			<div class="mb-4 relative">
				<label class="text-neutral-700 text-opacity-80 text-base font-semibold leading-snug">
					Select a course
				</label>

				<select
					bind:value={selectedCourse}
					class="w-full h-10 bg-gray-50 rounded-md border border-gray-300 px-4"
				>
					<option value="" disabled>Select a course</option>
					<option value="UI/UX Course">UI/UX Course</option>
					<option value="Web Development">Web Development</option>
					<option value="Project Management">Project Management</option>
				</select>
			</div>
		</div>

		<div class=" p-4 flex justify-end">
			<Button variant="secondary">Apply Now</Button>
		</div>
	</form>
</div>
