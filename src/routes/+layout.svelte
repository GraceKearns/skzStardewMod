<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import CursorRing from '$lib/components/CursorRing.svelte';
	import NavBar from '$lib/components/NavBar.svelte';
	import Footer from '$lib/components/Footer.svelte';
	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>
<CursorRing />
<div class="layout-flex">
	<NavBar/>
	<main class="main-flex">{@render children()}</main>
	<Footer/>
</div>
<style>
.layout-flex {
	display: flex;
	flex-direction: column;
	min-height: 100vh;
}
.main-flex {
	flex: 1 1 auto;
	display: flex;
	flex-direction: column;
}
</style>
