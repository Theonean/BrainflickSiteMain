<script lang="ts">
	// TODO: replace placeholder URLs, copy and screenshot paths with real ones
	const wishlistUrl = 'https://store.steampowered.com/app/YOUR_APP_ID';
	const pressKitUrl = '/presskit';

	const screenshots = [
		{ src: '/screenshots/01.png', alt: 'Screenshot 1' },
		{ src: '/screenshots/02.png', alt: 'Screenshot 2' },
		{ src: '/screenshots/03.png', alt: 'Screenshot 3' },
		{ src: '/screenshots/04.png', alt: 'Screenshot 4' }
	];

	const links = [
		{ label: 'Steam', href: wishlistUrl },
		{ label: 'Discord', href: 'https://discord.gg/YOUR_INVITE' },
		{ label: 'X / Twitter', href: 'https://x.com/YOUR_HANDLE' },
		{ label: 'YouTube', href: 'https://youtube.com/@YOUR_HANDLE' }
	];

	let email = $state('');
	let status: 'idle' | 'sending' | 'done' | 'error' = $state('idle');

	async function subscribe(event: SubmitEvent) {
		event.preventDefault();
		status = 'sending';
		try {
			// TODO: point this at your newsletter endpoint
			const res = await fetch('/api/subscribe', {
				method: 'POST',
				headers: { 'Content-Type': 'application/json' },
				body: JSON.stringify({ email })
			});
			status = res.ok ? 'done' : 'error';
		} catch {
			status = 'error';
		}
	}
</script>

<svelte:head>
	<title>Brainflick</title>
</svelte:head>

<!-- 1. Top of page: wishlist now -->
<section class="hero">
	<h1>Brainflick</h1>
	<a class="wishlist" href={wishlistUrl} target="_blank" rel="noopener noreferrer">
		Wishlist now
	</a>
</section>

<!-- 2. Subscribe to newsletter -->
<section id="newsletter">
	<h2>Subscribe to the newsletter</h2>
	{#if status === 'done'}
		<p role="status">Thanks, you're subscribed.</p>
	{:else}
		<form onsubmit={subscribe}>
			<label for="email" class="visually-hidden">Email address</label>
			<input
				id="email"
				type="email"
				required
				placeholder="Your email address"
				autocomplete="email"
				bind:value={email}
			/>
			<button type="submit" disabled={status === 'sending'}>
				{status === 'sending' ? 'Subscribing…' : 'Subscribe'}
			</button>
		</form>
		{#if status === 'error'}
			<p role="alert">Something went wrong. Check your email address and try again.</p>
		{/if}
	{/if}
</section>

<!-- 3. About the game -->
<section id="about">
	<h2>About the game</h2>
	<p>
		Describe the game here: what the player does, what makes it different, and what to expect
		at launch.
	</p>
</section>

<!-- 4. Screenshots -->
<section id="screenshots">
	<h2>Screenshots</h2>
	<div class="screenshots">
		{#each screenshots as shot}
			<img src={shot.src} alt={shot.alt} loading="lazy" />
		{/each}
	</div>
</section>

<!-- 5. Links -->
<section id="links">
	<h2>Links</h2>
	<ul>
		{#each links as link}
			<li>
				<a href={link.href} target="_blank" rel="noopener noreferrer">{link.label}</a>
			</li>
		{/each}
	</ul>
</section>

<!-- 6. Press kit link -->
<section id="press">
	<a href={pressKitUrl}>Press kit</a>
</section>

<style lang="scss">
	section {
		width: 100%;
		max-width: 60rem;
		margin: 0 auto;
		padding: 2.5rem 0;
		text-align: center;
	}

	h1,
	h2 {
		margin: 0 0 1rem;
	}

	p {
		max-width: 65ch;
		margin: 0 auto;
		line-height: 1.6;
	}

	a {
		color: inherit;
		text-underline-offset: 0.2em;
	}

	a:focus-visible,
	button:focus-visible,
	input:focus-visible {
		outline: 2px solid currentColor;
		outline-offset: 4px;
	}

	/* 1. Hero */
	.hero {
		padding-top: 0;
	}

	.wishlist {
		display: inline-block;
		font-size: 1.5rem;
		font-weight: 700;
		text-decoration: underline;
		text-decoration-thickness: 3px;
	}

	/* 2. Newsletter: no boxes, underline-only input */
	form {
		display: flex;
		justify-content: center;
		align-items: baseline;
		flex-wrap: wrap;
		gap: 1rem;
	}

	input {
		min-width: 16rem;
		padding: 0.4rem 0;
		font: inherit;
		color: inherit;
		background: none;
		border: none;
		border-bottom: 2px solid currentColor;
		border-radius: 0;
	}

	input::placeholder {
		color: inherit;
		opacity: 0.6;
	}

	button {
		padding: 0;
		font: inherit;
		font-weight: 700;
		color: inherit;
		background: none;
		border: none;
		text-decoration: underline;
		text-underline-offset: 0.2em;
		cursor: pointer;
	}

	button:disabled {
		opacity: 0.6;
		cursor: wait;
	}

	/* 4. Screenshots */
	.screenshots {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr));
		gap: 1rem;
	}

	.screenshots img {
		display: block;
		width: 100%;
		height: auto;
	}

	/* 5. Links */
	ul {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		gap: 0.5rem 2rem;
		margin: 0;
		padding: 0;
		list-style: none;
	}

	.visually-hidden {
		position: absolute;
		width: 1px;
		height: 1px;
		overflow: hidden;
		clip: rect(0 0 0 0);
		white-space: nowrap;
	}
</style>