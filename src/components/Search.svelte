<script>
    import { inputSearch } from '../store'
    let inp = ''

    $: inp, $inputSearch = inp
</script>

<input type="text" bind:value={ inp }>

<style>
    input {
        width: 300px;
        margin-top: 20px;
        padding: 10px;
        font-size: 20px;
        border: 1px solid #999;
        outline: none;
        transition: all .1s ease;
    }

    input:hover {
        border: 1px solid #777;
    }
    
    input:focus {
        border: 1px solid #000;
    }

    @media (max-width: 400px) {
        input {
            width: 100%;
        }
    }
</style>