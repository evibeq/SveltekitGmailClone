<script>
    import GButton from '$lib/header/googleButton.svelte'
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
    <img src="/svg/menu.svg" alt="menu">
</div>
{:else}
<div class="button" class:menuOpen={!invisible}>
    <img src="/svg/menu.svg" alt="menu">
</div>
{/if}
<div class="googleMenu" use:clickOutside on:click_outside={closePanel} class:invisible={invisible}>
    <div class="container first">
        <GButton link="https://myaccount.google.com/" src="/account.png" name="Account" account=1/>
        <GButton link="https://www.google.com/" src="/png/search.png" name="Search"/>
        <GButton link="https://www.google.it/maps/" src="/png/maps.png" name="Maps"/>
        <GButton link="https://www.youtube.com/" src="/png/youtube.png" name="Youtube"/>
        <GButton link="https://play.google.com/" src="/png/play.png" name="Play"/>
        <GButton link="https://mail.google.com/" src="/png/gmail.png" name="Gmail"/>
        <GButton link="https://drive.google.com/" src="/png/drive.png" name="Drive"/>
        <GButton link="https://calendar.google.com/" src="/png/calendar.png" name="Calendar"/>
        <GButton link="https://translate.google.com/" src="/png/translate.png" name="Translate"/>
        <GButton link="https://photos.google.com/" src="/png/photos.png" name="Photos"/>
        <GButton link="https://news.google.com/" src="/png/news.png" name="News"/>
        <GButton link="https://meet.google.com/" src="/png/meet.png" name="Meet"/>
        <GButton link="https://chat.google.com/" src="/png/chat.png" name="Chat"/>
        <GButton link="https://duo.google.com/about/" src="/png/duo.png" name="Duo"/>
    </div>
    <div class="container">
        <GButton link="https://shopping.google.com/" src="/png/shopping.png" name="Shopping"/>
        <GButton link="https://docs.google.com/" src="/png/docs.png" name="Docs"/>
        <GButton link="https://books.google.com/" src="/png/books.png" name="Books"/>
        <GButton link="https://blogger.google.com/" src="/png/blogger.png" name="Blogger"/>
        <GButton link="https://contacts.google.com/" src="/png/contacts.png" name="Contacts"/>
        <GButton link="https://hangouts.google.com/" src="/png/hangouts.png" name="Hangouts"/>
        <GButton link="https://finance.google.com/" src="/png/finance.png" name="Finance"/>
        <GButton link="https://sheets.google.com/" src="/png/sheets.png" name="Sheets"/>
        <GButton link="https://slides.google.com/" src="/png/slides.png" name="Slides"/>
        <GButton link="https://keep.google.com/" src="/png/keep.png" name="Keep"/>
        <GButton link="https://jamboard.google.com/" src="/png/jamboard.png" name="Jamboard"/>
        <GButton link="https://classroom.google.com/" src="/png/classroom.png" name="Classroom"/>
        <GButton link="https://earth.google.com/" src="/png/earth.png" name="Earth"/>
        <GButton link="https://podcasts.google.com/" src="/png/podcasts.png" name="Podcasts"/>
        <GButton link="https://one.google.com/" src="/png/googleOne.png" name="One"/>
        <GButton link="https://travel.google.com/" src="/png/travel.png" name="Travel"/>
        <GButton link="https://forms.google.com/" src="/png/forms.png" name="Forms"/>
    </div>
</div>

<style>
    .invisible {
        display: none;
    }

    .menuOpen {
        background-color: rgba(255, 255, 255, 0.2);
    }

    .googleMenu {
        position: absolute;
        overflow-y: scroll;
        top: 60px;  
        right: 10px;
        height: 500px;
        width: 300px;
        border-radius: 10px;
        background-color: #2c2c2c;
        box-shadow: 0px 0px 15px -2px black;
    }

    .container {
        display: flex;
        flex-wrap: wrap;
        gap: 15px;
        margin: 15px;
        
    }

    .first {
        border-bottom: 1px solid rgba(255, 255, 255, 0.2);
        padding-bottom: 10px;
    }

    ::-webkit-scrollbar {
        width: 8px;
    }
 
    /* Handle */
    ::-webkit-scrollbar-thumb {
        background: #595959;
        border-radius: 10px;
    }
</style>