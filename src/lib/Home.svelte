<div class='container'>
    <div class='left'>
        <iframe
            class="youtube"
            src="https://www.youtube.com/embed/XGxkeV0wUZ8?si=aMgM5mbIUFxNcdvC?autoplay=1&mute=1"
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
    </div>
    <div class='right'>
        <h1>CannonKeep</h1>
        <h2>
            Build <br>
            Defend <br>
            Persist.
        </h2>
        <br>
        <p>Backpack battles meets tower defense! Place and merge buildings onto the grid to grow your defenses. Expand your city's borders to increase your damage and scavenge the underground for resources.</p>
    </div>
</div>

<style lang="scss">
    h1 {
        margin: 0;
    }

    .container {
        display: grid;
        grid-template-columns: 3fr 1fr;
        gap: 2rem;
        width: 100%;
        height: auto;
    }

    .left {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        gap: 3vh;

        height: auto;
        border: 2px solid blue;

    }

    .right {
        border: 2px solid red;
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