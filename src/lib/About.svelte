<script>
    import logo from "$lib/assets/brainflick_logo_text_white.svg";
    import SocialLinks from "./atoms/SocialLinks.svelte";
</script>

<div class="container">
    <img class="logo" src={logo} alt="Brainflick" />
    <h1>Hey there!</h1>
    <p>
        We are Brainflick, a indie game studio based in Zurich, Switzerland, founded by Robin Welmers and Manuel Ineichen in 2025. Together, we create small games that make you think!
    </p>
    <div class="socials">
        <SocialLinks />
    </div>
</div>

<style lang="scss">
    .logo {
        display: block;
        width: min(100%, 24rem);
        height: auto;
        margin: 0 auto 2rem;
    }

    .socials {
        margin: 1.5rem 0 0 -10px; // lines the first icon up with the text, despite its tap target padding
    }
</style>