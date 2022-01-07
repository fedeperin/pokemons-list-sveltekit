<script>
    export let pokemon
</script>

<div class="card">
    <img src={ pokemon.img } alt={ pokemon.name }>
    <p>{pokemon.name}</p>
</div>

<style>
    .card {
        box-shadow: 0 0 4px -2px #000;
        border-radius: 2px;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        padding: 10px;
    }

    p {
        font-weight: bold;
        text-transform: uppercase;
    }
</style>