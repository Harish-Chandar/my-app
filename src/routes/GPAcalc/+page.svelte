<script>
    import Nested from "./NestedClass.svelte";
    let classes = [];
    let x;
    function newClass(){
        x = "<Nested></Nested>";
    }
</script>

<h1> GPA Calculator </h1>

<button on:click={newClass}>+</button>
{
    @html x
}
<Nested></Nested>