<script>
    import Header from '$lib/header/header.svelte'
    import LeftNav from '$lib/leftNav.svelte'
    import RightNav from '$lib/rightNav.svelte'  
    import Settings from '$lib/settings.svelte'
    import {settingsVisible} from '$lib/utils/store.js'
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap" rel="stylesheet">
</svelte:head>

<div class="main">
        <div class="header"><Header/></div>
        <div class="container">
            <div class="leftNav"><LeftNav/></div>
            <div class="slot"><slot></slot></div>
            {#if ($settingsVisible)}
            <div class="settings" ><Settings/></div>
            {:else}
            <div class="settings invisible" ><Settings/></div>
            {/if}
            <div class="rightNav"><RightNav/></div>
        </div>
</div>

<style>
    :global(body) {
        font-family: 'Roboto', sans-serif;
        font-weight: 400;
        background-color: #111111;
        color: white;
        margin: 0;
        padding: 0;
    }

    :global(a, a:hover, a:active, a:visited) {
        text-decoration: none;
        color: white;
    }

    :global(.button) {
        cursor: pointer;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        width: 50px;
        border: 0;
        border-radius: 50%;
        background-color: transparent;
    }

    :global(.button:hover) {
        background-color: rgba(255, 255, 255, 0.2);
    }

    .main {
        position: absolute;
        height: 100%;
        width: 100%;
        display: flex;
        flex-direction: column;
    }

    .header {
        padding: 8px 0 8px 0;
    }

    .container {
        flex: 1;
        display: flex;
        justify-content: space-between;
    }

    .leftNav {
        flex: 0 0 250px;
    }

    .settings {
        flex: 0 0 300px;
        background-color: rgba(255, 255, 255, 0.8);
        border-radius: 16px;
        margin-left: 10px;
        margin-bottom: 20px;
    }

    .invisible {
        display: none;
    }

    .rightNav {
        flex: 0 0 50px;
    }

    .slot {
        background-color: #2c2c2c;
        border-radius: 10px;
        margin-bottom: 20px;
        flex: 1;
    }
    
</style>