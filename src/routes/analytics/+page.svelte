<script>
	import SideNav from '$lib/components/layout/Dashboard/SideNav/SideNav.svelte';
	import Analytics from './Analytics.svelte';
</script>

<svelte:head>
	<title>Analytics | Dashboard</title>
	<meta name="description" content="Dashboard this app" />
</svelte:head>

<div class="text-column">
	<SideNav />
	<Analytics />
</div>
