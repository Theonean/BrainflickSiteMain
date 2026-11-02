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
        gap: 2rem;
        width: min(100%, $column-width);
        height: auto;
    }

    .description {
        width: 100%;
        font-size: 1.25rem;
    }

    .youtube {
        display: block;
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
        padding-block: 2rem;
        text-align: center;

        h2 {
            margin-bottom: 1.25rem;
        }

        a {
            @include button;
        }
    }
</style>