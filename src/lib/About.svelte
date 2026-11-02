<script>
    import SocialLinks from "./atoms/SocialLinks.svelte";
</script>

<div class="container">
    <h1>Hey! We are Brainflick</h1>
    <p>
        We are an indie game studio based in Zurich, Switzerland, founded by Robin Welmers and Manuel Ineichen in 2025. Together, we create small games that make you think!
    </p>
    <div class="socials">
        <SocialLinks />
    </div>
</div>

<style lang="scss">
    .socials {
        margin: 1.5rem 0 0 -10px; // lines the first icon up with the text, despite its tap target padding
    }
</style>