<script>
    import {clickOutside} from '$lib/utils/clickOutside.js';

    let invisible = true;

    //click on button to open panel
    function changeVisibility() {
        if (invisible) {
            invisible = false;
        }
    }

    //click outside to close panel
    function closePanel(event) {
        if (!invisible) {
            invisible = true;
        }
    }
</script>

{#if invisible}
<div class="button" on:click={changeVisibility} class:menuOpen={!invisible}>
    <img src="/svg/help.svg" alt="info">
</div>
{:else}
<div class="button" class:menuOpen={!invisible}>
    <img src="/svg/help.svg" alt="info">
</div>
{/if}
<div class="helpPanel" use:clickOutside on:click_outside={closePanel} class:invisible={invisible}>
    <a href="https://github.com/evibeq">Created by @evibeq with SvelteKit</a>
</div>

<style>
    .helpPanel {
        position: fixed;
        display: flex;
        align-items: center;
        padding: 20px;
        top: 60px;  
        right: 60px;
        height: 50px;
        border-radius: 10px;
        background-color: #2c2c2c;
        box-shadow: 0px 0px 15px -2px black;
    }

    .invisible {
        display: none;
    }

    .menuOpen {
        background-color: rgba(255, 255, 255, 0.2);
    }
</style>
