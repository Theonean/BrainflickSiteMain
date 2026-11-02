<script>
    import { resolve } from "$app/paths";
    import NewsletterSignup from "./atoms/NewsletterSignup.svelte";
    import ScreenshotCarousel from "./atoms/ScreenshotCarousel.svelte";

    // the steam widget's layout breaks below this width, so narrower screens get it at full size but scaled down as a whole
    const steamFullWidth = 646;
    const steamHeight = 190;

    let steamWidth = $state(steamFullWidth);
    let steamScale = $derived(Math.min(1, steamWidth / steamFullWidth));
</script>

<div class='container'>
    <iframe
        class="youtube"
        src="https://www.youtube.com/embed/Ra2v1Sp98Ks?autoplay=1&mute=1"
        title="CannonKeep Trailer on YouTube"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin"
        allowfullscreen
    >
    </iframe>
    <div class="steam" bind:clientWidth={steamWidth} style:height="{steamHeight * steamScale}px">
        <iframe
            title="Cannon Keep Steampage embedded"
            src="https://store.steampowered.com/widget/3755200/"
            frameborder="0"
            style:width="{steamWidth / steamScale}px"
            style:height="{steamHeight}px"
            style:transform="scale({steamScale})">
        </iframe>
    </div>
    <p class='description'>Build your city block by block and defeat waves of mechs in this tower defense roguelike! Combine powerful cannons with unique effects to survive the unforgiving wasteland and explore the underground to gather resources and find powerful relics.</p>
        <section class="press">
        <h2>Want to cover Cannon Keep?</h2>
        <a href={resolve("/press-kit")}>Check out our press kit</a>
    </section>
    <ScreenshotCarousel />
    <NewsletterSignup />
</div>

<style lang="scss">
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 3vh;
        width: min(100%, max(40vw, 30rem));
        height: auto;
    }

    .description {
        width: 100%;
        padding: 1.5rem;
        color: white;
        border-radius: 8px;
        border: 2px solid $orange;
    }

    .youtube {
        aspect-ratio: 16 / 9;
        width: 100%;
        height: auto;
    }

    .steam {
        width: 100%;
        overflow: hidden;

        iframe {
            display: block;
            transform-origin: top left;
        }
    }

    // same look as the newsletter section and its button
    .press {
        width: 100%;
        padding-bottom: 2.5rem;
        text-align: center;

        h2 {
            margin-bottom: 1rem;
        }

        a {
            display: inline-block;
            padding: 0.6rem 1.25rem;
            color: white;
            background-color: $orange;
            border-radius: 8px;
            text-decoration: none;
            transition: background-color 0.2s, color 0.2s;

            &:hover {
                color: $orange;
                background-color: white;
            }
        }
    }
</style>