<script>
    // our export lets (props)
    export let value = 2; // doubled value in case yes.
    export let toDouble = false;
    export let clicks = 1;
    export let pClass = "text-lg text-gray-600 mb-8";
    export let buttonClass = "bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75";
    export let toCenter = true;


    //funcs
    function onclick() {
        clicks = clicks + 1;
        value = clicks * 2;
    }

</script>

{#if toCenter === true}
    <center>
       <br>
       <br>
       <br>
       <br>
       <button on:click={onclick} class={buttonClass}>
           Increment
       </button>

       {#if toDouble != false}
           <br>
           <p class={pClass} >You have clicked {clicks}, times! Thats {value} Doubled!</p>
       {:else}
           <br>
           <p class={pClass} >You have clicked {clicks} times!</p>
       {/if}
    </center>
{:else}
    <button on:click={onclick} class={buttonClass}>
        Increment
    </button>

    {#if toDouble != false}
        <p class={pClass} >You have clicked {clicks}, times! Thats {value} Doubled!</p>
    {:else}
        <p class={pClass} >You have clicked {clicks} times!</p>
    {/if}

{/if}