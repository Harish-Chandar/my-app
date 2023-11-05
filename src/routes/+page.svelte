<script>
    let count = 0;
    let paracontent = "see look it changed";
    function increment(){
        count ++;
        if (paracontent === "see look it changed"){
            paracontent = "it changed again wow";
        } else {
            paracontent = "see look it changed"
        }
    }
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<button on:click={increment}> {count} </button>
<p id="para"> {paracontent} </p>

<style>
    
</style>