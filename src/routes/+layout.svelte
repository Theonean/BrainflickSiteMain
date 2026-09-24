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
		grid-template-rows: auto 10%;
		min-height: 100vh;
	}

	.content {
		@include center;
		padding: ($navbar-height + 5vh) 20vw 5vh 20vw;
        background:
			url('$lib/assets/clouds.png') no-repeat top,
			linear-gradient(to bottom, #f8ead5, #f6e2c7, #f5d9b9, #f4d1ab, #f3c89e, #edbb91, #e6af85, #e0a279, #d28f6b, #c47b5f, #b66953, #a75649);
		background-origin: border-box;
		background-size: contain;
        -webkit-background-size: cover;
        -moz-background-size: cover;
        -o-background-size: cover;
	}
</style>