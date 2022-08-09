<script>
    let invisible = true;
    let minimized = false;

    let recipes = "";
    let subject = "";
    let text = "";

    //click to open panel
    function changeVisibility() {
        if (invisible) {
            invisible = false;
        }
    }

    //click to close panel
    function closePanel() {
        if (!invisible) {
            invisible = true;
            minimized = false;
        }
    }

    function minimize(){
        if (minimized) {
            minimized = false;
        } else {
            minimized = true;
        }
    }

    function remove() {
        recipes = "";
        subject = "";
        text = "";
        closePanel();
    }
</script>

<div class="composeBtn" on:click={changeVisibility}>
    <img class="createImg" src="/png/create.png" alt="create">
    <p class="dark">Compose</p>
</div>
<div class="compose" class:invisible={invisible}>
    <div class="header">
        {#if (subject.length === 0)}
        <p>New message</p>
        {:else}
        <p>{subject}</p>
        {/if}
        <div class="buttons">
            {#if (minimized)}
            <div class="cButton" on:click={minimize}><img class="cImg" src="/png/maximize.png" alt="minimize"></div>
            {:else}
            <div class="cButton" on:click={minimize}><img class="cImg" src="/png/minimize.png" alt="minimize"></div>
            {/if}
            <div class="cButton" on:click={closePanel}><img class="cImg" src="/png/close.png" alt="close"></div>
        </div>
    </div>
    <div class="textArea" class:invisible={minimized}>
        <div class="inputLine"><input type="text" placeholder="Recipients" bind:value={recipes}></div>
        <div class="inputLine"><input type="text" placeholder="Subject" bind:value={subject}></div>
        <div class="text"><textarea name="" id="" cols="30" rows="10" bind:value={text}></textarea></div>
        <div class="bottom">
            <div class="cButton send"><p class="sendText">Send</p></div>
            <div class="cButton" on:click={remove}><img class="cImg" src="/png/delete.png" alt="clean"></div>
        </div>
    </div>
</div>

<style>
    .createImg {
        margin-right: 18px;
    }

    .send {
        border-radius: 20px;
        background-color: #0b57d0;
        cursor: pointer;
        display:flex;
        justify-content:center;
        align-items:center;
        height: 34px;
    }

    .cButton {
        cursor: pointer;
        display: flex;
        justify-content: center;
    }

    .cImg {
        filter: brightness(0%);
        margin-left: 18px;
    }

    .sendText {
        font-weight: 400;
        color: white;
        margin: 0px 24px 0px 24px;
    }

    .composeBtn {
        cursor: pointer;
        height: 60px;
        width: 140px;
        margin: 10px;
        background-color: white;
        border-radius: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    p {
        margin: 0;
        color: #474747;
    }

    .header {
        flex: 0 0 40px;
        padding: 10px;
        display: flex;
        justify-content: space-between;
        color: #041e49;
        background-color: #f2f2f2;
        border-radius:  16px 16px 0 0;
    }

    .textArea {
        display: flex;
        flex-direction: column;
        background-color: white;
        padding: 10px;
    }

    input {
        border: none;
        outline: none;
    }

    textarea {
        resize: none;
        border: none;
        outline: none;
        width: 100%;
        height: 100%;
        margin-top: 8px;
    }

    .text {
        flex: 0 0 400px;
    }

    .bottom {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-top: 16px;
        flex: 0 0 40px;
    }

    ::-webkit-scrollbar {
        display: none;
    }

    .buttons {
        display: flex;
    }

    .inputLine {
        padding: 4px 0 4px 0;
        border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    }

    .invisible {
        display: none;
    }

    .compose {
        position: fixed;
        right: 80px;
        bottom: 0px;
        width: 600px;
    }
</style>
