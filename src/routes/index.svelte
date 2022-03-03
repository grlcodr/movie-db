<script context="module">
    export async function load({fetch}){
        const res = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=f82084b0ae7fedc85d09a83f06f8baa1&language=en-US&page=1`);
        const data = await res.json();
        console.log(data)
        if (res.ok){
            return {
                props: { popular: data.results }
            };
        }
    }
</script>

<script>
    import PopularMovies from '../components/PopularMovies.svelte';
    export let popular;
</script>

<section>
    <PopularMovies {popular}/>
</section>

