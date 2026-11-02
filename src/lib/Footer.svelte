<script>
    import { resolve } from "$app/paths";
</script>

<div class="footer-container">
    <div class="left">
        <p class="copyright">Copyright © 2026 Brainflick</p>
    </div>
    <div class="right">
        <a href={resolve("/impressum")}>Impressum</a>
        <a href={resolve("/privacy")}>Privacy Policy</a>
    </div>
</div>

<style lang="scss">
    .footer-container {
        display: grid;
        grid-template-columns: 1fr auto;
        gap: 1rem;
        align-items: center;
        width: 100%;
        padding: 16px;
        border-top: 2px solid $orange;

        @media (max-width: 800px) {
            grid-template-columns: 1fr;
            gap: 1.5rem;
            text-align: center;
        }
    }

    .right {
        display: flex;
        justify-content: flex-end;
        gap: 1.5rem;

        @media (max-width: 800px) {
            justify-content: center;
        }
    }

    p {
        margin: 0;
        color: $background;
    }

    a {
        color: white;

        &:hover {
            color: $purple;
        }
    }
</style>