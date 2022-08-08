<script>
    import SearchFilms from "./searchFilms.svelte";
    import MyFilms from "./myFilms.svelte";
</script>


<nav>
    <SearchFilms/>
    <a href="/">Film Database</a>
    <MyFilms/>
</nav>

<style>
    nav {
        display: flex;
        min-height: 10vh;
        align-items: center;
        justify-content: space-evenly;
    }

    a {
        text-decoration: none;
        color: black;
        font-weight: 600;
        font-size: 1.2rem;
        text-transform: uppercase;
    }
</style>