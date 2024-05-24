<script>
    import CounterScript from "../CounterScript.svelte"
    let setup_pkg = {
        "pClass": "text-lg text-gray-600 mb-8",
        "buttonClass": "bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75"
    }
    // has to be separate from pkg because funni
    let toDouble = false;
    let toCenter = true;
    let selectedButtonClass = "bg-blue-500 text-white font-semibold py-3 px-5 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75";

    function svetlog() {
            if (toCenter) {
                toCenter = false
            } else {
                toCenter = true;
            }
        
    }

    function svetlog_b() {
        
            if (toDouble) {
                toDouble = false
            } else {
                toDouble = true;
            }
        
        
    }
</script>

<center>
    <br>
    <a href="/" class={selectedButtonClass}>Home</a>
    <a href="/about" class={setup_pkg.buttonClass}>About</a>
    
</center>

<CounterScript bind:toDouble={toDouble} bind:toCenter={toCenter} {...setup_pkg}/>

<button on:click={svetlog_b} class="bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75">
    toDouble = {toDouble}
</button>

<button on:click={svetlog} class="bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75">
    toCenter = {toCenter}
</button>