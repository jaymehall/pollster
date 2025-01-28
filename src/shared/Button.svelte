<script>
    export let type = "primary";
    export let flat = false;
    let inverse = false;
</script>

<button class={type}>
    <slot></slot>
</button>

<style>
    button{
        border: 0;
        cursor: pointer;
        border-radius: 6px;
        padding: 8px 12px;
        font-weight: 800;
        box-shadow: 1px 2px 3px rgba(0,0,0,0.2);
    }
    .primary{
        background: #0665a8;
        color: white;
    }
    .secondary{
        background: #1adccb;
        color: white;
    }
    .flat{
        box-shadow: none;
    }
    .primary.inverse{
        background: white;
        color: #0665a8;
        border: 2px solid #0665a8;
    }
    .secondary.inverse{
        color: #1adccb;
        background: white;
        border: 2px solid #1adccb;
    }
</style>