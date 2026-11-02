<script>
    import { afterNavigate } from "$app/navigation";
    import { resolve } from "$app/paths";
    import PageNav from "./atoms/PageNav.svelte";
    import logo from "$lib/assets/brainflick_logo_white.svg";

    let menuOpen = $state(false);

    afterNavigate(() => {
        menuOpen = false;
    });
</script>

<svelte:window onkeydown={(event) => { if (event.key === "Escape") menuOpen = false; }} />

<div class="navbar">
    <a class="home" href={resolve("/cannon-keep")}>
        <img
            class="logo"
            src={logo}
            alt="Brainflick home"
        />
    </a>
    <PageNav options={['Cannon Keep', 'About us', 'Newsletter', 'Press kit']} open={menuOpen}/>
    <button
        class="menu-button"
        aria-label={menuOpen ? "Close menu" : "Open menu"}
        aria-expanded={menuOpen}
        onclick={() => menuOpen = !menuOpen}
    >
        <svg viewBox="0 0 24 24" width="32" height="32" aria-hidden="true">
            {#if menuOpen}
                <path d="M5 5 19 19M19 5 5 19" />
            {:else}
                <path d="M3 6H21M3 12H21M3 18H21" />
            {/if}
        </svg>
    </button>
</div>

<style lang="scss">
    .navbar {
        // equal outer columns keep the nav links centered on the page, whatever the logo's width
        display: grid;
        grid-template-columns: 1fr auto 1fr;
        align-items: center;

        position: fixed;
        top: 0;
        z-index: 10;
        background: $orange;
        width: 100%;
        min-height: $navbar-height;
        padding-inline: $gutter;
        font-size: 1.125rem;

        // the open menu becomes a second row, so the navbar grows to fit it
        @media (max-width: 800px) {
            grid-template-columns: 1fr auto;
            grid-template-rows: $navbar-height auto;
        }
    }

    .home {
        justify-self: start;
        display: block;

        &:hover {
            background: none;
        }

        .logo {
            display: block;
            width: 3rem;
        }
    }

    .menu-button {
        display: none;
        padding: 6px;
        margin-right: -6px; // lines the icon up with the page gutter, despite its tap target padding
        color: white;
        background: none;
        border: none;
        cursor: pointer;

        @media (max-width: 800px) {
            display: block;
            grid-row: 1;
            grid-column: 2;
        }

        &:hover {
            color: $purple;
        }

        svg {
            display: block;
            fill: none;
            stroke: currentColor;
            stroke-width: 2;
            stroke-linecap: round;
        }
    }
</style>
