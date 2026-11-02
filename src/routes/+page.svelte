<script>
	import Home from "$lib/Home.svelte";

	// tells google what to call the site in search results, it only reads this from the domain's home page
	const siteName = JSON.stringify({
		"@context": "https://schema.org",
		"@type": "WebSite",
		name: "Brainflick",
		url: "https://brainflick.ch/"
	});
</script>

<svelte:head>
	<title>Cannon Keep - Brainflick</title>
	<link rel="canonical" href="https://brainflick.ch/" />
	{@html `<script type="application/ld+json">${siteName}<\/script>`}
</svelte:head>

<!-- Header and Footer are added in layout.svelte -->

<Home />
