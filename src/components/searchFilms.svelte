<script>
    let inputValue = ''
    let active = false

    import {goto} from '$app/navigation'

    function submitSearch(){
        goto("/search/" + inputValue)
    }

    function clearSearch(){
        inputValue = ''
    }
</script>


<form on:submit|preventDefault={submitSearch} on:submit={clearSearch} class="search-form"> 
    <input on:focus={() => (active = true)} bind:value={inputValue} type="text" name="search-film" id="search-film" placeholder="Search Film">

    {#if inputValue !== ''}
    <button>go</button>
    {/if}
</form>

<style>
    .search-form{
        position: relative;
    }

    input {
        width: 100%;
        height: 100%;
        border: none;
        background-color: white;
        color: black;
        font-size: 1rem;
        padding: .5rem 1rem 0;
        text-transform: uppercase;

        position: relative;
    }

    input:focus-visible {
        outline: none;
    }

    input::after {
        content: '';

        position: absolute;
        width: 100%;
        height: 1px;

        bottom: 0;
        left: 0;

        transform: scaleX(0);

        background-color: gray;
    }

    input::after:focus-visible {
        transform: scaleX(1);
    }

    button {
        position: absolute;
        height: 100%;
        cursor: pointer;

        border: none;
        background-color: transparent;
        color: black;
        font-weight: 600;
        text-transform: uppercase;
        font-size: 1rem;
        bottom: -10%;

        padding:0;

        animation: button-appear 500ms ease-out forwards;
    }

    @keyframes button-appear {
        0% {
            opacity: 0;
        }

        100% {
            opacity: 1;
        }
    }
</style>