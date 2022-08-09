<script>
    import {settingsVisible} from '$lib/utils/store.js'

    function changeVisibility() {
        if ($settingsVisible) {
            $settingsVisible = false;
        } else {
            $settingsVisible = true;
        }
    }
</script>

<div class="header">
    <div class="container">
        <p>Settings</p>
        <div class="button" on:click={changeVisibility}><img src="/svg/cross.svg" alt="close"></div>
    </div>
</div>

<style>
    .header {
        color: black;
    }

    .container {
        margin: 10px;
        display: flex;
        justify-content: space-between;
    }

    p {
        margin-left: 10px;
    }

    img {
        filter: invert(80%);
    }
</style>