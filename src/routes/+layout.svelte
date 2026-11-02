<script lang="ts">
	import favicon from '$lib/assets/brainflick_logo.svg';
	import Footer from '$lib/Footer.svelte';
	import Navbar from '$lib/Navbar.svelte';
    import '$lib/scss/app.scss'
	let { children } = $props();
</script>

<svelte:head>
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

	// fixed so the gradient stays screen-height on pages that scroll
	.main-grid::before {
		content: '';
		position: fixed;
		inset: 0;
		z-index: -1;
		background: $purple;
	}

	.content {
		@include center;
		padding: ($navbar-height + 5vh) 20vw 5vh 20vw;

		@media (max-width: 800px) {
			padding-inline: 5vw;
		}
	}
</style>