<script>
    import Compose from '$lib/composePanel.svelte';

    let visibleCat = false;
    function collapseCat() {
        if (visibleCat) {
            visibleCat = false;
        } else {
            visibleCat = true;
        }
    }

    let visibleMore = false;
    function collapseMore() {
        if (visibleMore) {
            visibleMore = false;
        } else {
            visibleMore = true;
        }
    }
</script>

<Compose />
<div class="leftBtn"> <div class="innerBtn"> <img src="/png/inbox.png" alt="inbox"> Inbox </div> </div>
<div class="leftBtn"> <div class="innerBtn"> <img src="/png/starred.png" alt="starred"> Starred</div> </div>
<div class="leftBtn"> <div class="innerBtn"> <img src="/png/snoozed.png" alt="snoozed"> Snoozed</div> </div>
<div class="leftBtn"> <div class="innerBtn"> <img src="/png/important.png" alt="important"> Important</div> </div>
<div class="leftBtn"> <div class="innerBtn"> <img src="/png/sent.png" alt="sent"> Sent</div> </div>

<div class="leftBtn" on:click={collapseCat}> <div class="innerBtn"> <img src="/png/categories.png" alt="categories"> Categories</div> </div>
<div class:invisibleCat={!visibleCat}>
    <div class="leftBtn"> <div class="innerBtn inner"> <img class="invert" src="/png/social.png" alt="social"> Social</div> </div>
    <div class="leftBtn"> <div class="innerBtn inner"> <img class="invert" src="/png/updates.png" alt="updates"> Updates</div> </div>
    <div class="leftBtn"> <div class="innerBtn inner"> <img class="invert" src="/png/forums.png" alt="forums"> Forums</div> </div>
    <div class="leftBtn"> <div class="innerBtn inner"> <img class="invert" src="/png/promotions.png" alt="promotions"> Promotions</div> </div>
</div>

<div class="leftBtn" on:click={collapseMore}> <div class="innerBtn"> <img class:rotated={visibleMore} src="/png/more.png" alt="more">More</div> </div>
<div class:invisibleMore={!visibleMore}>
    <div class="leftBtn"> <div class="innerBtn inner"> <img src="/png/chats.png" alt="chats">Chats</div> </div>
    <div class="leftBtn"> <div class="innerBtn inner"> <img class="invert" src="/png/scheduled.png" alt="scheduled">Scheduled</div> </div>
    <div class="leftBtn"> <div class="innerBtn inner"> <img class="invert" src="/png/drafts.png" alt="drafts">Drafts</div> </div>
    <div class="leftBtn"> <div class="innerBtn inner"> <img class="invert" src="/png/allMail.png" alt="allmail">All Mail</div> </div>
    <div class="leftBtn"> <div class="innerBtn inner"> <img class="invert" src="/png/spam.png" alt="spam">Spam</div> </div>
    <div class="leftBtn"> <div class="innerBtn inner"> <img class="invert" src="/png/delete.png" alt="bin">Bin</div> </div>
</div>

<style>
    img {
        margin-right: 18px;
    }

    .invert {
        filter: invert(100%);
    }

    .inner {
        margin-left: 20px;
    }

    .rotated {
        transform: rotate(180deg);
    }

    .invisibleCat {
        display: none;
    }

    .invisibleMore {
        display: none;
    }

    .leftBtn {
        max-width: 240px;
        cursor: pointer;
    }

    .leftBtn:hover {
        background-color: rgba(255, 255, 255, 0.2);
        border-radius: 0 16px 16px 0;
    }

    .innerBtn {
        height: 32px;
        padding: 0 12px 0 26px;
        display: flex;
        align-items: center;
    }
</style>