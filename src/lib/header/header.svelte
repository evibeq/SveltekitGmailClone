<script>
    import SearchBar from '$lib/header/searchBar.svelte'
    import GoogleMenu from '$lib/header/googleMenu.svelte'
    import HelpPanel from '$lib/header/helpPanel.svelte'
    import {settingsVisible} from '$lib/utils/store.js'

    function changeVisibility() {
        if ($settingsVisible) {
            $settingsVisible = false;
        } else {
            $settingsVisible = true;
        }
    }
</script>

<header>
    <div class="logo"><img src="/logo.png" alt="Cmail"></div>
    <div class="center">
        <div class="searchBar"><SearchBar/></div>
        <div class="buttons">
            <HelpPanel/>
            <div class="button" on:click={changeVisibility}><img src="/svg/settings.svg" alt="settings"></div>
            <GoogleMenu/>
        </div>
    </div>
    <div class="button account" on:click={() => window.open("https://myaccount.google.com/", "_blank")}><img class="userImg" src="/account.png" alt="account"></div>
</header>

<style>
    header {
        display: flex;
        justify-content: space-between;
    }

    .logo {
        flex: 0 0 250px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .center {
        flex: 1;
        display: flex;
        justify-content: space-between;
    }

    .searchBar {
        flex: 0 1 700px;
    }

    .buttons {
        display: flex;
    }

    .account {
        flex: 0 0 50px;
        margin-right: 10px;
    }

    .userImg {
        height: 35px;
        width: 35px;
        border-radius: 50%;
    }
</style>
