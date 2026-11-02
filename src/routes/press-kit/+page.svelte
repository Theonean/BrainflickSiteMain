<script>
	import capsuleMain from "$lib/assets/presskit/CK_Capsule_Main.jpg";
	import capsuleVertical from "$lib/assets/presskit/CK_Capsule_Vertical.jpg";
	import keyart from "$lib/assets/presskit/CK_Keyart.jpg";
	import keyartFull from "$lib/assets/presskit/CK_Keyart_Full.jpg";
	import gameLogo from "$lib/assets/presskit/CK_Logo.png";
	import studioLogo from "$lib/assets/presskit/Brainflick_Full.png";
	import studioLogoLight from "$lib/assets/presskit/Brainflick_Full_Light.png";
	import ss1 from "$lib/assets/screenshots/ss1.png";
	import ss2 from "$lib/assets/screenshots/ss2.png";
	import ss3 from "$lib/assets/screenshots/ss3.png";
	import ss4 from "$lib/assets/screenshots/ss4.png";
	import ss5 from "$lib/assets/screenshots/ss5.png";
	import ss6 from "$lib/assets/screenshots/ss6.png";
	import ss8 from "$lib/assets/screenshots/ss8.png";

	const assetsFolder = "https://drive.google.com/drive/folders/14ANLdAqZyW7HMQ_bQowI_aBMRanuU5k9";
	const spritesFolder = "https://drive.google.com/drive/folders/14AjPieVOatMBo2yqmh4FFnXULMFxTzRm";
	const driveFile = (/** @type {string} */ id) => `https://drive.google.com/file/d/${id}/view`;

	const about = [
		{
			title: "Build",
			text: "Backpack battles meets tower defense! Place and merge buildings onto the grid to grow your defenses. Expand your city's borders to increase your damage and scavenge the underground for resources."
		},
		{
			title: "Defend",
			text: "Watch your defenses cut down waves of enemies and turn the tides of combat with the commander's powerful ability. Combine turrets with various effects to maximize your city's defensive capabilities."
		},
		{
			title: "Persist",
			text: "Find your way to play by combining different buildings into your own unique strategy. Face growing hordes of enemies and take down their boss to claim a piece of the wasteland for yourself."
		}
	];

	const videos = [
		{ label: "Trailer (CK_Trailer.mp4)", id: "1al9NsjWzqnv0_sDTKIe_hhvhXonEQbSc" },
		{ label: "15-second teaser (CK_15s.mp4)", id: "1Nt1XtrBptZ_RG-ysqnZgcZ0dMuPcZFB2" },
		{ label: "Tower clip (CK_Tower.mp4)", id: "1UvdR70oETrYwP6KYZthEBX1BF3lkOI-b" },
		{ label: "Combat showcase (CannonKeep_CombatShowcase.gif)", id: "1uZy83LZdI4RecQcpX3IZVPYADV8zgJMx" }
	];

	const screenshots = [
		{ src: ss1, id: "1Yrfbk6dvss3B8SGHi--trM1CzZVVzH1q", alt: "The fortress firing chain lightning at flying enemies under a teal aurora sky" },
		{ src: ss2, id: "1DSk0zDzGU-y5umMoE3Fpz0Twfsish-HV", alt: "A fortress of merged buildings on a desert grid at sunset, with a shop of new buildings on the left" },
		{ src: ss3, id: "1Ja3csT6c8S5P4TFo5YkJZRmO0nSBX2Nd", alt: "Underground mining view with ore deposits and Recon, Dig and Mine cards" },
		{ src: ss4, id: "1t-S5qcC8ReuUVUt7B1aKpbMJJpjZnwfn", alt: "The fortress firing on walking machines and airships under a purple night sky" },
		{ src: ss5, id: "1txOguf1Ylgq4tOllkcGG3yotyu9vuW_l", alt: "A giant spider-legged machine with glowing red eyes towering over the fortress" },
		{ src: ss6, id: "1Uh8t6-G38fm_yj0K-kq08xl8I63FucNR", alt: "The fortress fighting a huge armored boss machine with a health bar across the top" },
		{ src: ss8, id: "1y6ZIfgwFQxl5-_CcAlMh07ymXFeJfKxQ", alt: "The fortress shooting at flying and walking enemies in a desert at dusk" }
	];

	const logosAndArt = [
		{ src: gameLogo, id: "1ceZ4GYe3SQmx8ZUstGjoCMs-vB2eVow6", label: "Cannon Keep logo" },
		{ src: keyart, id: "17NhQCmj-mp0o8Becf2tRyS20u--wub-8", label: "Key art" },
		{ src: keyartFull, id: "1g8xW9-grh11C9GGoPugWy74vH5TgY1Yn", label: "Key art, wide" },
		{ src: capsuleMain, id: "1YN1LjwEvdrAkGvyrJvu2jhEzaGFZELAU", label: "Main capsule" },
		{ src: capsuleVertical, id: "1xGSJtvNvnEnia7tA-nq10aDmlREX9wb9", label: "Vertical capsule" },
		{ src: studioLogoLight, id: "1H6uwmXhhHPk0-qkABo_z-FfbWRkrv8hQ", label: "Brainflick logo, light" },
		{ src: studioLogo, id: "1a7OOIEoZDrA_N6N75zkdov-60YiKGQ8u", label: "Brainflick logo, dark", onWhite: true }
	];
</script>

<svelte:head>
	<title>Cannon Keep Press Kit</title>
</svelte:head>

<!-- Header and Footer are added in layout.svelte -->

<div class="container">
	<header>
		<img class="hero" src={capsuleMain} alt="Cannon Keep key art with the game's logo" />
		<h1>Cannon Keep Press Kit</h1>
	</header>

	<div class="overview">
		<dl class="facts">
			<dt>Title</dt>
			<dd>Cannon Keep</dd>
			<dt>Release</dt>
			<dd>2 December 2026</dd>
			<dt>Developer</dt>
			<dd>Studio Brainflick, based in Zurich, Switzerland</dd>
			<dt>Publisher</dt>
			<dd>Brainflick</dd>
			<dt>Genre</dt>
			<dd>Tower defense roguelike</dd>
			<dt>Platform</dt>
			<dd>Steam (Windows)</dd>
			<dt>Price</dt>
			<dd>TBA</dd>
			<dt>Languages</dt>
			<dd>English, French, German, Spanish (Latin America), Japanese, Simplified Chinese, Traditional Chinese, Russian, Portuguese (Brazil)</dd>
			<dt>Steam</dt>
			<dd><a href="https://store.steampowered.com/app/3755200/Cannon_Keep/" target="_blank" rel="noopener noreferrer">Cannon Keep on Steam</a></dd>
			<dt>Socials</dt>
			<dd><a href="https://linktr.ee/brainflick" target="_blank" rel="noopener noreferrer">linktr.ee/brainflick</a></dd>
			<dt>Contact</dt>
			<dd><a href="mailto:support@brainflick.ch">support@brainflick.ch</a></dd>
		</dl>

		<div class="descriptions">
			<section>
				<h2>Short Description</h2>
				<p>Build your city block by block and defeat waves of mechs in this tower defense roguelike! Combine powerful cannons with unique effects to survive the unforgiving wasteland and explore the underground to gather resources and find powerful relics.</p>
			</section>

			<section>
				<h2>About this Game</h2>
				{#each about as block}
					<h3>{block.title}</h3>
					<p>{block.text}</p>
				{/each}
			</section>

			<section>
				<h2>About Studio Brainflick</h2>
				<p>Studio Brainflick was created by Robin Welmers and Manuel Ineichen in 2025. The two met during their Game Design studies and decided to pursue their passion as a team. Under the mentorship of Philomena Schwab, co-founder of Stray Fawn Studio, and Thomas Gervraud, creator of Brotato, they developed the concept for their first commercial project Cannon Keep.</p>
			</section>
		</div>
	</div>

	<section>
		<h2>Trailer</h2>
		<iframe
			src="https://www.youtube.com/embed/Ra2v1Sp98Ks"
			title="Cannon Keep trailer on YouTube"
			frameborder="0"
			allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
			referrerpolicy="strict-origin-when-cross-origin"
			allowfullscreen
			loading="lazy"
		></iframe>
		<ul>
			{#each videos as video}
				<li><a href={driveFile(video.id)} target="_blank" rel="noopener noreferrer">{video.label}</a></li>
			{/each}
		</ul>
	</section>

	<section>
		<h2>Screenshots</h2>
		<div class="grid screenshots">
			{#each screenshots as shot}
				<a href={driveFile(shot.id)} target="_blank" rel="noopener noreferrer">
					<img src={shot.src} alt={shot.alt} loading="lazy" />
				</a>
			{/each}
		</div>
	</section>

	<section>
		<h2>Logo & Key Art</h2>
		<div class="grid assets">
			{#each logosAndArt as asset}
				<a class="captioned" href={driveFile(asset.id)} target="_blank" rel="noopener noreferrer">
					<img class:on-white={asset.onWhite} src={asset.src} alt="" loading="lazy" />
					<span>{asset.label}</span>
				</a>
			{/each}
		</div>
	</section>

	<section>
		<h2>All Assets</h2>
		<ul>
			<li><a href={assetsFolder} target="_blank" rel="noopener noreferrer">Full press kit folder on Google Drive</a></li>
			<li><a href={spritesFolder} target="_blank" rel="noopener noreferrer">Game sprites</a></li>
		</ul>
	</section>
</div>

<style lang="scss">
	.container {
		width: min(100%, $column-width-wide);
		display: flex;
		flex-direction: column;
		gap: 3.5rem;
	}

	.hero {
		display: block;
		width: 100%;
		height: auto;
	}

	h1 {
		margin: 2.5rem 0 0;
	}

	h2 {
		margin-bottom: 1rem;
	}

	h3 {
		margin-top: 1.25rem;
		margin-bottom: 0.25rem;
	}

	.overview {
		display: grid;
		grid-template-columns: minmax(0, 1fr) minmax(0, 2fr);
		gap: 3.5rem;
		align-items: start;

		// the two sides get cramped well before phone width
		@media (max-width: 1000px) {
			grid-template-columns: minmax(0, 1fr);
			gap: 3rem;
		}
	}

	.descriptions {
		display: flex;
		flex-direction: column;
		gap: 3rem;
	}

	.facts {
		display: grid;
		grid-template-columns: auto 1fr;
		gap: 0.75rem 1.5rem;

		@media (max-width: 800px) {
			grid-template-columns: 1fr;
			gap: 0;

			dd {
				margin-bottom: 0.75rem;
			}
		}
	}

	dt {
		font-weight: bold;
		color: $background;
	}

	dd {
		overflow-wrap: anywhere;
	}

	ul {
		padding-left: 1.25rem;
	}

	li + li {
		margin-top: 0.25rem;
	}

	iframe {
		display: block;
		aspect-ratio: 16 / 9;
		width: 100%;
		height: auto;
		margin-bottom: 1.25rem;
	}

	.grid {
		display: grid;
		gap: 1rem;
		align-items: start;

		a {
			display: block;
			color: white;
			font-weight: normal;
			text-decoration: none;

			&:hover {
				color: $orange;
				background: none;

				img {
					outline-color: $orange;
				}
			}
		}

		img {
			display: block;
			width: 100%;
			height: auto;
			outline: 2px solid transparent;
			transition: outline-color 0.15s;
		}
	}

	.screenshots {
		grid-template-columns: repeat(auto-fill, minmax(min(100%, 16rem), 1fr));

		// one big one on top, so the seven screenshots fill the grid evenly
		a:first-child {
			grid-column: 1 / -1;
		}
	}

	// these all have different shapes, so each sits centered in a tile of the same size
	.assets {
		grid-template-columns: repeat(auto-fill, minmax(min(100%, 13rem), 1fr));

		img {
			aspect-ratio: 16 / 9;
			padding: 0.75rem;
			object-fit: contain;
			background: $purple-light;
		}
	}

	.captioned span {
		display: block;
		padding-top: 0.5rem;
	}

	img.on-white {
		background: white;
	}
</style>
