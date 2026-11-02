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
        <a
            href={resolve(getPathName(option))}
            class="option {page.url.pathname === getPathName(option) ? 'selected' : ''}"
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
        gap: 6vw;
        width: 100%;

        @media (max-width: 800px) {
            display: none;
            grid-row: 2;
            grid-column: 1 / -1;
            flex-direction: column;
            align-items: center;
            gap: 1rem;
            padding: 1rem 0;

            &.open {
                display: flex;
            }
        }
    }

    a.option {
        border: red 5px;
        color: white;
        font-weight: bold;
        text-decoration: none;
    }
    a.option:hover {
        color: $purple;
    }
    a.option.selected {
        background-image: linear-gradient(to top,)
    }

</style>