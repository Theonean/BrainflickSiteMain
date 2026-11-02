<script lang="ts">
    import { page } from "$app/state";
    import { resolve } from "$app/paths";
    import { type RouteId } from "$app/types";
    // make sure the strings in here are captialized, apparently capitalization in js is an absolute clownshow
    // open only matters on mobile, where the links are hidden behind the navbar's menu button
    let { options, open = false }: { options: Array<string>, open?: boolean } = $props();

    // this turns e.g. 'About us' into 'about-us'
    // does it mean, that the option names need to match the route names for this component to work? perhaps...
    const getPathName = (option: string) => {
        return '/' + option.toLowerCase().replace(' ', '-') as RouteId;
    }
</script>

<nav class="container" class:open>
    {#each options as option}
        {@const href = resolve(getPathName(option))}
        <a
            {href}
            class="option"
            class:selected={page.url.pathname === href}
            aria-current={page.url.pathname === href ? 'page' : undefined}
        >
            {option}
        </a>
    {/each}
</nav>

<style lang="scss">
    .container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        gap: clamp(2rem, 5vw, 4rem);
        width: 100%;

        @media (max-width: 800px) {
            display: none;
            grid-row: 2;
            grid-column: 1 / -1;
            flex-direction: column;
            align-items: center;
            gap: 1rem;
            padding: 0.5rem 0 1.5rem;

            &.open {
                display: flex;
            }
        }
    }

    a.option {
        color: white;
        font-weight: bold;
        text-decoration: none;
        white-space: nowrap;
        transition: color 0.15s;
    }
    a.option:hover {
        color: $purple;
    }
    a.option.selected {
        text-decoration: underline;
        text-decoration-thickness: 3px;
        text-underline-offset: 0.35em;
    }
</style>