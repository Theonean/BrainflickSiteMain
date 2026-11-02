<script lang="ts">
    import ss1 from "$lib/assets/screenshots/ss1.png";
    import ss3 from "$lib/assets/screenshots/ss3.png";
    import ss4 from "$lib/assets/screenshots/ss4.png";
    import ss5 from "$lib/assets/screenshots/ss5.png";
    import ss6 from "$lib/assets/screenshots/ss6.png";
    import ss7 from "$lib/assets/screenshots/ss7.png";
    import ss8 from "$lib/assets/screenshots/ss8.png";

    const screenshots = [
        { src: ss1, alt: "The fortress firing chain lightning at flying enemies under a teal aurora sky" },
        { src: ss3, alt: "Underground mining view with ore deposits and Recon, Dig and Mine cards" },
        { src: ss4, alt: "The fortress firing on walking machines and airships under a purple night sky" },
        { src: ss5, alt: "A giant spider-legged machine with glowing red eyes towering over the fortress" },
        { src: ss6, alt: "The fortress fighting a huge armored boss machine with a health bar across the top" },
        { src: ss7, alt: "A choice of three upgrade cards: Red Paint, Galvanized Square Steel and Really Cool Flame Sticker" },
        { src: ss8, alt: "The fortress shooting at flying and walking enemies in a desert at dusk" }
    ];

    let current = $state(0);
    let paused = $state(false);
    let strip = $state<HTMLElement>();

    const show = (index: number) => {
        current = (index + screenshots.length) % screenshots.length;
    }

    // moves on by itself, except while tabbing through the controls with a keyboard. Choosing a screenshot restarts the timer
    $effect(() => {
        if (paused || window.matchMedia("(prefers-reduced-motion: reduce)").matches) return;
        const next = current + 1;
        const timer = setTimeout(() => show(next), 5000);
        return () => clearTimeout(timer);
    });

    // keeps the selected thumbnail in view. Only scrolls the strip, scrollIntoView would also move the page
    $effect(() => {
        const thumbnail = strip?.children[current] as HTMLElement | undefined;
        if (!strip || !thumbnail) return;
        strip.scrollTo({ left: thumbnail.offsetLeft - (strip.clientWidth - thumbnail.offsetWidth) / 2, behavior: "smooth" });
    });
</script>

<section
    class="carousel"
    aria-label="Screenshots"
    onfocusin={(event) => paused = (event.target as HTMLElement).matches(":focus-visible")}
    onfocusout={() => paused = false}
>
    <div class="main">
        {#each screenshots as shot, i}
            <img class:visible={i === current} src={shot.src} alt={i === current ? shot.alt : ""} loading="lazy" />
        {/each}
    </div>
    <div class="controls">
        <button class="arrow" aria-label="Previous screenshot" onclick={() => show(current - 1)}>
            <svg viewBox="0 0 24 24" width="24" height="24" aria-hidden="true"><path d="M15 5 8 12 15 19" /></svg>
        </button>
        <div class="thumbnails" bind:this={strip}>
            {#each screenshots as shot, i}
                <button
                    class="thumbnail"
                    class:selected={i === current}
                    aria-label="Show screenshot {i + 1}"
                    aria-current={i === current}
                    onclick={() => show(i)}
                >
                    <img src={shot.src} alt="" loading="lazy" />
                </button>
            {/each}
        </div>
        <button class="arrow" aria-label="Next screenshot" onclick={() => show(current + 1)}>
            <svg viewBox="0 0 24 24" width="24" height="24" aria-hidden="true"><path d="M9 5 16 12 9 19" /></svg>
        </button>
    </div>
</section>

<style lang="scss">
    .carousel {
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        width: 100%;
    }

    .main {
        position: relative;
        aspect-ratio: 16 / 9;
        width: 100%;
        background: black;

        img {
            position: absolute;
            inset: 0;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity 0s 0.3s; // the old screenshot stays up until the new one has faded in on top of it

            &.visible {
                z-index: 1;
                opacity: 1;
                transition: opacity 0.3s;
            }
        }
    }

    .controls {
        display: flex;
        align-items: center;
        gap: 0.25rem;
    }

    .thumbnails {
        position: relative;
        display: flex;
        gap: 0.5rem;
        flex-grow: 1;
        min-width: 0;
        padding: 2px;
        overflow-x: auto;
        scrollbar-width: none;
    }

    button {
        background: none;
        border: none;
        color: white;
        cursor: pointer;
    }

    .thumbnail {
        display: block;
        flex: 0 0 23%;
        aspect-ratio: 16 / 9;
        opacity: 0.6;
        outline: 2px solid transparent;
        transition: opacity 0.2s;

        img {
            display: block;
            width: 100%;
            height: 100%;
        }

        &:hover, &.selected {
            opacity: 1;
        }

        &.selected {
            outline-color: $orange;
        }
    }

    .arrow {
        flex: none;
        padding: 10px 6px; // with the 24px icon this makes a 44px tall tap target
        transition: color 0.15s;

        &:hover {
            color: $orange;
        }

        svg {
            display: block;
            fill: none;
            stroke: currentColor;
            stroke-width: 2;
            stroke-linecap: round;
            stroke-linejoin: round;
        }
    }

    .thumbnail:focus-visible, .arrow:focus-visible {
        outline: 2px solid white;
        outline-offset: 2px;
    }
</style>
