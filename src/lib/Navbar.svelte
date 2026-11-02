<script>
    import PageNav from "./atoms/PageNav.svelte";
    import logo from "$lib/assets/brainflick_logo_white.svg";
</script>
<div class="navbar">
    <a href="https://linktr.ee/brainflick">
        <img
            class="logo"
            src={logo}
            alt="Brainflick Studios Logo"
        />
    </a> 
    <PageNav options={['Cannon Keep', 'About us', 'Newsletter']}/>
</div>

<style lang="scss">
    .navbar {
        // equal outer columns keep the nav links centered on the page, whatever the logo's width
        display: grid;
        grid-template-columns: 1fr 3fr 1fr;
        align-items: center;

        /* could add a transparency gradient here maybe*/
        position: fixed;
        top: 0;
        background: $orange;
        overflow: hidden;
        width: 100%;
        padding: 10px;
        font-family: 'Roboto', sans-serif;
        font-size: 1.5rem;

        @media (max-width: 800px) {
            font-size: 1rem;
        }

        a {
            padding: 0;
            font-weight: normal;
            text-decoration: none;
            color: white;
        }

        a:hover {
            color: $purple;
        }

        .logo {
            width: 4rem;
            padding: 0;
        }
    }
</style>