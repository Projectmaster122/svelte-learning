<script>
    import CounterScript from "../CounterScript.svelte"
    let setup_pkg = {
        "pClass": "text-lg text-gray-600 mb-8",
        "buttonClass": "bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75",
    }
    // has to be separate from pkg because funni
    let toDouble = false;
    let toCenter = true;
    let selectedButtonClass = "bg-blue-500 text-white font-semibold py-3 px-5 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75";
    let options_visible = false;
    let options_text = "Show Settings"
    let value = 2;
    let clicks = 1;
    $: value = clicks * 2
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

    function svetlog_c() {
        if (options_visible) {
            options_visible = false;
            options_text = "Show Settings";
        }else {
            options_visible = true;
            options_text = "Hide Settings";
        }
    }
</script>

<title>Main Page</title>

<center>
    <br>
    <a href="/" class={selectedButtonClass}>Home</a>
    <a href="/about" class={setup_pkg.buttonClass}>About</a>
    
</center>

<CounterScript bind:toDouble={toDouble} bind:toCenter={toCenter} {...setup_pkg} bind:clicks={clicks} bind:value={value}/>

<button on:click={svetlog_c} class={!options_visible ? "bg-blue-500 text-white font-semibold py-3 px-5 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75" : "bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75"}>
    {options_text}
</button>

<br>
<br>

{#if options_visible}
<button on:click={svetlog_b} class="bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75">
    toDouble = {toDouble}
</button>

<button on:click={svetlog} class="bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75">
    toCenter = {toCenter}
</button>
<br>
<br>

<p>Starting value</p>
<input type="number" bind:value={clicks} class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block max-w-xs p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"/>

{/if}