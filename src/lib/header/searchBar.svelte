<script>
    export const label = "Search in emails"

    let formStyle;
    const onFocus =() => formStyle="background-color: white;";
	const onBlur =() => formStyle="background-color: #474747;";
</script>

<form class="searchBar" style={formStyle}>
    <input type="text" placeholder={label} on:focus={onFocus} on:blur={onBlur}>
    <div class="button search"><img class="icon" src="/svg/search.svg" alt="search"></div>
    <div class="button filter"><img class="icon" src="/svg/filter.svg" alt="filter"></div>
</form>

<style>
    .searchBar {
        display: flex;
        justify-content: space-between;
        border-radius: 8px;
        background-color: #474747;
        transition: color 100ms linear;
    }

    .search {
        order: 1;
    }

    .filter {
        order: 3;
    }

    input::placeholder{
        color: white;
    }

    input:focus::placeholder {
        color: #474747;
        transition: color 100ms linear;
    }

    input {
        flex: 1;
        order: 2;
        box-sizing: border-box;
        border: none;
        color: white;
        font-size: 14px;
        background-color: transparent;
        padding: 12px 20px 12px 0;
    }

    input:focus {
        color: #474747;
        outline: none;
    }

    input:focus ~ .button .icon {
        filter: invert(80%);
    }
</style>