<script context='module'>
    export async function load({fetch, params}){
         const response = await fetch(
            `https://api.themoviedb.org/3/search/movie?api_key=7c05bda317c7da73685e9abba8c1e28f&language=en-US&query=${params.id}&page=1&include_adult=false`
            )
 
         const data = await response.json()

         if(response.ok){
             return{
                 props: { searchedFilm: data.results }
             }
         }
    } 
 </script>

 <script>
    import FilmCard from "../../components/filmCard.svelte";
    export let searchedFilm
 </script>

<section>
    <h1>Search results</h1>
    <div class="searched-films">
        {#each searchedFilm as film}
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

    .searched-films {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        grid-template-rows: repeat(auto-fit, minmax(450px, 1fr));

        grid-column-gap: 1.5rem;
        grid-row-gap: 1.7rem;
 
        margin-top: 2rem;
    }
</style>