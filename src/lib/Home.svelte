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
    <iframe
        class="steam"
        title="Cannon Keep Steampage embedded"
        src="https://store.steampowered.com/widget/3755200/"
        frameborder="0">
    </iframe>
    <p class='description'>Backpack battles meets tower defense! Place and merge buildings onto the grid to grow your defenses. Expand your city's borders to increase your damage and scavenge the underground for resources.</p>
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
        aspect-ratio: 16 / 9;
        width: 100%;
        height: auto;
        max-height: 190px;
    }
</style>