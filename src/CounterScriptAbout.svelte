<script>
    let count = 0;
    let funny_visible = false;
    $: {
        if (count == 10) {
            count = 0;
            funny_visible = true;
        }
    }
    function onclick() {
        count += 1;
    }
</script>


<button on:click={onclick} class="bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-7">
    Your count: {count}
</button>

<br>

{#if funny_visible}
    Told you it was worse.
{/if}