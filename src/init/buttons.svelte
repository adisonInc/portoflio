<script>
    export let func;
    export let cont;
</script>


<button on:click|once={func}>{cont}</button>
<style>

    button{
        color: whitesmoke;
        background-color: #190061;
        border-color: #190061;
        border-radius: 8%;

    }
</style>
