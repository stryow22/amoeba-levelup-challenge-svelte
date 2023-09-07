<script>
	import EnrolForm from '$lib/components/Form/EnrolForm.svelte';
	import EnrolSection from './home/EnrolSection.svelte';
	import HeroSection from './home/HeroSection.svelte';
	import InstructorsSection from './home/InstructorsSection.svelte';
	import OfferSection from './home/OfferSection.svelte';
	import TrendingSection from './home/TrendingSection.svelte';
</script>

<svelte:head>
	<title>Home | Challenge</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<HeroSection />
	<EnrolSection />
	<OfferSection />
	<TrendingSection/>
	<InstructorsSection />
</section>

<style>
	/*  */
</style>
