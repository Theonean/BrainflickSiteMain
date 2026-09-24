<script>
    import PageNav from "./atoms/PageNav.svelte";
    import logo from "$lib/assets/brainflick_logo.svg";
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
    <div class="socials-container">
        <a href="https://store.steampowered.com/app/3755200/Cannon_Keep/">Steam</a>
        <a href="https://store.steampowered.com/app/3755200/Cannon_Keep/">Instagram</a>
    </div>
</div>

<style lang="scss">
    .navbar {
        display: flex;
        align-items: center;
        justify-content: space-between;

        /* could add a transparency gradient here maybe*/
        position: fixed;
        top: 0;
        background: linear-gradient(0, #f8ead500 0%, #f8ead5ff 100%);
        overflow: hidden;
        width: 100%;
        padding: 10px;
        
        a {
            padding: 0;
            font-weight: bold;
            color: $terracotta
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