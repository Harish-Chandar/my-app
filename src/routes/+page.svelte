<script>
    import Nested from './Nested.svelte';
    let count = 0;
    let arr = [13,42,5,46];
    let paracontent = "see look it changed";
    let firstname = "Harish";
    let lastname = "Chandar";
    $: fullname = lastname + ", " + firstname; // this will change the fullname value if the first or last names are ever changed
    function increment(){
        count ++; // [++] is a popular shorthand for [var = var + 1]
        if (paracontent === "see look it changed"){
            paracontent = "it changed again wow";
        } else {
            paracontent = "see look it changed";
        }
        arr.push(Math.floor(Math.random()*10)+1); // this does nothing without the next line
        arr = arr; // this updates the variable with an assignment, redundant in plain JS, but necessary here
        console.log(arr);
    }
    $: if (count > 10){
        paracontent = "count is getting a bit too high, I'll set it back down for you";
        count = 0;
    } // this performs actions whenever count gets too high
    $: console.log(`the count is ${count}`); // this outputs a message whenever count is changed
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<button on:click={increment}> {count} {count === 1 ? "count" : "counts"}</button>
<p id="para"> {paracontent} </p>
<h2> My name is {fullname}</h2>
<Nested ans={42} ></Nested>
<a href="/GPAcalc"> GPA Calculator </a>

<style>
    
</style>