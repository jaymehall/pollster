<script>
    export let tabs;
    export let activeTab;
</script>


<div class="tabs">
    <ul>
        {#each tabs as tab}
            <li>
                <div class:active={tab === activeTab}>{tab}</div>
            </li>
        {/each}
    </ul>
</div>

<style>
    .active {
        color: #0665a8;
        border-bottom: 2px solid #1adccb;
        padding-bottom: 8px;
    }
    .tabs {
        margin-bottom: 40px;

    }
    ul {
        display: flex;
        align-content: center;
        justify-content: center;
        padding: 0;
        list-style-type: none;
    }
    li {
        margin: 0 16px;
        font-size: 18px;
        cursor: pointer;
    }
</style>