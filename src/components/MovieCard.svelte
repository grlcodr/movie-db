<script>
    export let movie;
</script>

<div class="movie-card">
    <a href={`/movie/${movie.id}`}>
        <img src={`https://image.tmdb.org/t/p/original${movie.poster_path}`} alt="{movie.title}">
    </a>
    <div class="desc">
        <h2>{movie.title}</h2>
        <p>{movie.release_date}</p>
    </div>
</div>

<style>
    img {
        width: 100%;
        border-radius: 1rem;
        margin-bottom: 1rem;
    }

    h2 {
        font-size: 1.2rem;
    }
    
    .desc {
        height: 5vh;
    }
    p {
        font-size: 0.9rem;
    }

    .movie-card {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        padding: 1rem;
        align-items: center;
        text-align: center;
    }
</style>