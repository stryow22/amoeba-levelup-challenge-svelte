<script>
	import SideNav from '$lib/components/layout/Dashboard/SideNav/SideNav.svelte';
	import DashboardHome from './DashboardHome.svelte';
</script>

<svelte:head>
	<title>Dashboard</title>
	<meta name="description" content="Dashboard this app" />
</svelte:head>

<div class="text-column">
	<SideNav />
	<DashboardHome />
</div>
