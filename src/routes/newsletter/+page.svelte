<script>
	import NewsletterSignup from "$lib/atoms/NewsletterSignup.svelte";
</script>

<!-- Header and Footer are added in layout.svelte -->

<div class="container">
	<NewsletterSignup />
</div>

<style lang="scss">
	// same column width as the home page
	.container {
		width: min(100%, max(40vw, 30rem));
	}
</style>
