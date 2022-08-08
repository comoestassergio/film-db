<script context='module'>
    export async function load({fetch, params}){
         const response = await fetch(`https://api.themoviedb.org/3/movie/${params.id}?api_key=7c05bda317c7da73685e9abba8c1e28f&language=en-US`)
 
         const filmDetail = await response.json()
 
         if(response.ok){
             return{
                 props: { filmDetail }
             }
         }
    } 
 </script>

 <script>
    export let filmDetail
 </script>

 <div class="film-detail">
    <div class="img-container">
        <img src={'https://image.tmdb.org/t/p/original' + filmDetail.backdrop_path} alt={filmDetail.title}>
    </div>
    <div class="text-container">
        <h1 class="title">{filmDetail.title}</h1>
        <p class='tagline'>{filmDetail.tagline}</p>
        <div class="additional-info">
            <p class="duration"><span>Runtime:</span> {filmDetail.runtime} minutes</p>
            <p class="budget"><span>Budget:</span> ${filmDetail.budget}</p>
            <p class="rating"><span>Rating:</span> {Math.round(filmDetail.vote_average * 10) / 10}</p>
        </div>
        <p class="overview">{filmDetail.overview}</p>
    </div>
 </div>

 <style>
    .img-container {
        position: relative;
    }

    .text-container {
        padding-left: 3rem;
        padding-bottom: 1.5rem;

        position: fixed;
        bottom: 0;   
        background-color: white;

        width: 100%;
    }

    img {
        width: 100%;
    }

    .title {
        text-transform: uppercase;
    }

    .tagline {
        font-style: italic;
        color: rgb(68, 68, 68);
        margin-bottom: 2rem;
    }

    .overview {
        font-size: 1.2rem;
        line-height: 1.5;
    }

    .additional-info > p{
        margin: 0 0 .5rem;
    }

    span {
        font-weight: bold;
    }
 </style>