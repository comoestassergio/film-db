<script>
    export let film
</script>

{#if film.poster_path !== null}
<div class="film-card">
    <a href={'/film/' + film.id}>
        <img src={`https://image.tmdb.org/t/p/w500${film.poster_path}`} alt={film.title} height="350px"/>
    </a>
    <h2>{film.title}</h2>
    <p>Released: {film.release_date}</p>
</div>
{/if}

<style>
    img {
        border-radius: 1rem;

        transition: transform 200ms ease-out;
    }

    h2 {
        font-size: 1rem;
        text-transform: uppercase;
        text-align: center;
    }

    P {
        margin: 0;
        color: gray;
    }

    .film-card {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    img:hover {
        transform: scale(1.01);
    }
</style>