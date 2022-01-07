<script>
    import PokemonCard from './PokemonCard.svelte'
    import { inputSearch, actualPokemons } from '../store'

    $actualPokemons = []

    $: $inputSearch, fetch("https://pokeapi.co/api/v2/pokemon?limit=151")
        .then(res => res.json())
        .then(data => {
            let pokemonsWithData = []
            $actualPokemons = data.results
            $actualPokemons.forEach((poke, index) => {
                poke.img = `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${ index + 1 }.png`
                poke.id = index + 1

                pokemonsWithData = [...pokemonsWithData, poke]
            })
            $actualPokemons = pokemonsWithData
            $actualPokemons = $actualPokemons.filter(res => {
                return res.name.toUpperCase().includes($inputSearch.toUpperCase())
            })
            $actualPokemons = [...$actualPokemons]
        })
</script>

<div class="grid">
    {#each $actualPokemons as pokemon}
        <PokemonCard { pokemon } />
    {/each}
</div>

<style>
    .grid {
        width: 350px;
        margin-top: 40px;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-gap: 10px;
    }

    @media(max-width: 400px) {
        .grid {
            width: 100%;
            grid-template-columns: 1fr;
        }
    }
</style>