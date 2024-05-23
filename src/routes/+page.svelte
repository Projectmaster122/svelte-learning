<script>
    import CounterScript from "../CounterScript.svelte"
    let pkg = {
        "value": 2,
        "clicks": 1
    }
    // has to be separate from pkg because funni
    let toDouble = false;
    function svetlog() {
        if (toDouble) {
            toDouble = false
        }else {
            toDouble = true;
        }
        
    }
</script>

<CounterScript bind:toDouble={toDouble} {...pkg}/>

<button on:click={svetlog}>
    toDouble = {toDouble}
</button>
