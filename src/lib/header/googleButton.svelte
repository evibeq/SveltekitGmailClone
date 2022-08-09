<script>
    export let link;
    export let src;
    export let name;
    export let account = 0;

    let styleBg = "";
    if (account!==0) {
        styleBg = "height: 40px; border-radius: 100%";
    }

    function openNewtab() {
        window.open(link, "_blank");
    }
</script>

<div class="button" on:click={openNewtab}>
    <img class="rightIcon" src={src} alt={name} style={styleBg}>
    <p>{name}</p>
</div>

<style>
    .button {
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        flex: 0 0 77px;
        height: 77px;
        border-radius: 10px;
    }

    p {
        margin: 8px;
        font-size: 14px;
    }

    .rightIcon {
        height: 40px;
        width: 40px;
    }
</style>