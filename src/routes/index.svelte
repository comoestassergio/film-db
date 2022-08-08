<!-- 7c05bda317c7da73685e9abba8c1e28f -->

<script context='module'>
   export async function load({fetch}){
        const response = await fetch('https://api.themoviedb.org/3/movie/popular?api_key=7c05bda317c7da73685e9abba8c1e28f&language=en-US&page=1')

        const data = await response.json()

        if(response.ok){
            return{
                props: { popular: data.results }
            }
        }
   } 
</script>

<script>
    import PopularFilms from "../components/popularFilms.svelte";
    export let popular
    import global from '../global.css'
</script>

<section>
    <PopularFilms {popular}/>
</section>

