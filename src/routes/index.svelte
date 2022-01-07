<svelte:head>
    <title>Pokémon List</title>
</svelte:head>

<script>
    import Search from '../components/Search.svelte'
    import List from '../components/List.svelte'
</script>

<h1>Pokémon List</h1>
<Search />
<List />

<style>
    h1 {
        font-size: 35px;
        text-align: center;
    }
</style>