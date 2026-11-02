<script lang="ts">
	import favicon from '$lib/assets/brainflick_logo.svg';
	import Footer from '$lib/Footer.svelte';
	import Navbar from '$lib/Navbar.svelte';
    import '$lib/scss/app.scss'
	let { children } = $props();
</script>

<svelte:head>
	<title>Brainflick</title>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class='main-grid'>
	<Navbar />
	<div class='content'>
		{@render children()}
	</div>
	<Footer />
</div>

<style lang="scss">
	:root {
		overscroll-behavior: none;
	}

	.main-grid {
		display: grid;
		grid-template-rows: 1fr auto;
		grid-template-columns: minmax(0, 1fr); // stops wide content like the steam widget's frame from stretching the page
		min-height: 100vh;
	}

	.content {
		@include center;
		padding: ($navbar-height + 4rem) $gutter 5rem;

		@media (max-width: 800px) {
			padding-top: $navbar-height + 2rem;
			padding-bottom: 3rem;
		}
	}
</style>