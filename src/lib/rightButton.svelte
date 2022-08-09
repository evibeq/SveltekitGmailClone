<script>
    export let link;
    export let name;

    const src = "/png/" + name + ".png";

    function openNewtab() {
        window.open(link, "_blank");
    }
</script>

<div class="button" on:click={openNewtab}><img class="rightIcon" src={src} alt={name}></div>

<style>
    .button {
        width: auto;
    }

    .rightIcon {
        height: 30px;
        width: 30px;
    }
</style>