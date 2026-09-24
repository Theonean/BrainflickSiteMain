<script>
    import { resolve } from "$app/paths";
</script>

<div class="footer-container">
    <div class="left">
        <p class="copyright">Copyright © 2026 Brainflick Studios</p>
    </div>
    <div class="center">
        <a href={resolve("/impressum")}>Impressum</a>
        <a href={resolve("/privacy")}>Privacy Policy</a>
    </div>
    <div class="right">
        <div>Icons made from <a href="https://www.onlinewebfonts.com/icon">svg icons</a> is licensed by CC BY 4.0</div>
    </div>
</div>

<style lang="scss">
    .copyright {
        flex-grow: 1;
    }
    
    .footer-container {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        padding: 10px;
        background-color: #a75649;
    }

    p {
        margin: 0;
        color: $background;
    }
</style>