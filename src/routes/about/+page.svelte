<script>
    import CounterScriptAbout from "../../CounterScriptAbout.svelte";
    let setup_pkg = {
        "pClass": "text-lg text-gray-600 mb-8",
        "buttonClass": "bg-blue-500 text-white font-semibold py-2 px-4 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75",
        "selectedButtonClass": "bg-blue-500 text-white font-semibold py-3 px-5 rounded-md shadow-md transition-transform transform hover:scale-105 hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75"
    }
</script>

<title>About</title>

<center>
    <br>
    <a href="/" class={setup_pkg.buttonClass}>Home</a>
    <a href="/about" class={setup_pkg.selectedButtonClass}>About</a>
    <br>
    <br>
    <br>
    <h2>About</h2>

    Hello, this page is mainly to document my svelte learning process, although i do have the code on github if anyone new to svelte wants to learn a bit from my mistakes xD, cya!
    <br>
    P.S: for your enjoyment, heres a worse version of the counter you would otherwise see by pressing the "Home" Button.
    <br>
    <br>
    <CounterScriptAbout />
</center>