<script lang="ts">
	import EnrolSection from './home/EnrolSection.svelte';
	import CTASection from './home/CTASection.svelte';
	import HeroSection from './home/HeroSection.svelte';
	import InstructorsSection from './home/InstructorsSection.svelte';
	import OfferSection from './home/OfferSection.svelte';
	import TrendingSection from './home/TrendingSection.svelte';
	import Navbar from '$lib/components/layout/Navbar/Navbar.svelte';
	import Footer from '$lib/components/layout/Footer/Footer.svelte';
	import { onMount } from 'svelte';

	let isMobile: boolean;

function updateIsMobile() {
	isMobile = window.innerWidth <= 768;
}

onMount(() => {
	window.addEventListener('resize', updateIsMobile);
	updateIsMobile();
});
</script>

<svelte:head>
	<title>Home | Challenge</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<Navbar />
	<HeroSection />
	<EnrolSection />
	<OfferSection />
	<TrendingSection />
	<InstructorsSection />
	<CTASection/>

	{#if isMobile}
	<div hidden>
		<Footer />
	</div>
{:else}
	<Footer />
{/if}
</section>

<style>
	/*  */
</style>
