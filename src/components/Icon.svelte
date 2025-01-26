<script>
    export let icon;
    export let url;
    export let description;
</script>

<i class="icon-logo">
    <a rel="noreferrer" target="_blank" href={url}>
        <img src={icon} alt={description} />
    </a>
</i>

<style>
    .icon-logo {
        color: white;
        margin-right: 30px;
    }

    .icon-logo:hover,
    .icon-logo:focus,
    .icon-logo:active {
        -webkit-transform: scale(0.8);
        transform: scale(0.9);
    }
    img {
        max-width: 30px;
        border-radius: 20%;
    }
</style>