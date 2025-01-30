<script>
    import Icon from "./Icon.svelte";
</script>

<footer>
    <div class="icon-container">
            <Icon icon={"/img/githubLogo.png"} url="https://github.com/theprivacydev" description="Github Logo" />
            <Icon icon="/img/linkedInnLogo.png" url="https://www.linkedin.com/in/jayme-hall/" description="LinkedInnLogo" />
            <Icon icon={"/img/xLogo.jpg"} url="https://x.com/theprivacydev" description="X Logo" />
            <Icon icon="/img/emailLogo.jpg" url="mailto:theprivacydev@protonmail.com" description="Email Logo" />
    </div>
    <div class="code-link">
        <a href="https://github.com/theprivacydev/pollster" target="_blank" rel="noreferrer">
            View App Code
        </a>
    </div>
</footer>

<style>
     footer {
         background: #E1DFDFFF;
         padding: 20px;
         position: fixed;
         bottom: 0;
         width: 100%;
     }

     .icon-container {
         display: -webkit-box;
         display: -ms-flexbox;
         display: flex;
         -webkit-box-pack: center;
         -ms-flex-pack: center;
         justify-content: center;
         -webkit-box-align: center;
         -ms-flex-align: center;
         align-items: center;
     }
     .code-link{
         margin-top: 10px;
         display: flex;
         align-items: center;
         justify-content: center;
     }
</style>