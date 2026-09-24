<script lang="ts">
    import { page } from "$app/state";
    import { resolve } from "$app/paths";
    import { type RouteId } from "$app/types";
    // make sure the strings in here are captialized, apparently capitalization in js is an absolute clownshow
    let { options }: { options: Array<string>} = $props();

    // this turns e.g. 'About us' into 'about-us'
    // does it mean, that the option names need to match the route names for this component to work? perhaps...
    const getPathName = (option: string) => {
        return '/' + option.toLowerCase().replace(' ', '-') as RouteId;
    }
</script>

<nav class="container">
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
        justify-content: space-evenly;
        width: 100%;
        padding: 0 20% 0 20%;
    }

    a.option {
        border: red 5px;
    }
    a.option.selected {
        background-image: linear-gradient(to top,)
    }

</style>