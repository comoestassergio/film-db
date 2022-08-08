<script>
    export let popular
    import FilmCard from "./filmCard.svelte";
</script>

<section>
    <h1>Popular Films</h1>
    <div class="popular-films">
        {#each popular as film}
            <FilmCard {film}/>
        {/each}
    </div>
</section>

<style>

    section {
        margin: 2rem 3rem;
    }

    h1 {
        margin: 3rem 2rem 0;
        font-size: 2.5rem;
        text-transform: uppercase;
    }

    .popular-films {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        grid-template-rows: repeat(auto-fit, minmax(450px, 1fr));

        grid-column-gap: 1.5rem;
        grid-row-gap: 1.7rem;
 
        margin-top: 2rem;
    }
</style>