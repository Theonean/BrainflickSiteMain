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
    <PageNav options={['Home', 'About us']}/>
</div>

<style lang="scss">
    .navbar {
        display: flex;
        align-items: center;
        justify-content: space-between;

        /* could add a transparency gradient here maybe*/
        position: fixed;
        top: 0;
        background: $orange;
        overflow: hidden;
        width: 100%;
        padding: 10px;
        font-family: 'Roboto', sans-serif;
        font-size: 1.5rem;

        a {
            padding: 0;
            font-weight: normal;
            text-decoration: none;
            color: white;
        }

        a:hover {
            color: $text;
        }

        .logo {
            width: 4rem;
            padding: 0;
        }
    }
</style>