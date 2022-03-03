<script context="module">
    export async function load({fetch, params}){
        const res = await fetch(`https://api.themoviedb.org/3/movie/${params.id}?api_key=f82084b0ae7fedc85d09a83f06f8baa1&language=en-US`);
        const movieDetails = await res.json();
        if (res.ok){
            return {
                props: { movieDetails }
            };
        }
    }
</script>

<script>
    export let movieDetails;
</script>

<div class="movie-details">
    <div class="img-cont">
        <img src={`https://image.tmdb.org/t/p/original${movieDetails.backdrop_path}`} alt={movieDetails.title}>
    </div>
    <div class="text-cont">
        <h1 class="title">{movieDetails.original_title}</h1>
        <h2 class="tagline">{movieDetails.tagline}</h2>
        <p class="overview">{movieDetails.overview}</p>
        <div class="genres">
            {#each movieDetails.genres as genre}
                <h4 class="genre">{genre.name}</h4>
            {/each}
        </div>
        <p class="release"><span>Release Date:</span> {movieDetails.release_date}</p>
        <p class="runtime"><span>Runtime:</span> {movieDetails.runtime} minutes</p>
        
    </div>
</div>

<style>
    h1 {
        padding: 1rem 0rem 2rem;
    }

    p {
        padding: 1rem 0rem;
    }
    .movie-details {
        margin: 2rem 20%;
    }
    .img-cont img {
        width: 100%;
    }
    .genres {
        display: flex;
    }

    .genre {
        padding-right: 10px;
    }
    span {
        font-weight: bold;
    }
</style>
