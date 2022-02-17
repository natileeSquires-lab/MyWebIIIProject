<script>

//variable
let selectedSpell;


//function for API
    async function loadSpells(searchQuery=""){
         const response = await fetch(`https://www.dnd5eapi.co/api/classes/paladin/spells${searchQuery}?format=j1`);
        const result = await response.json(); 
        return result;
    }

    // function for dropdown
   function selectionChanged(event){
         if(!event.target.value) return;
     }

</script>

<style>    
    /* h1 is the header */
        h1{
            font-family:verdana;
            font-size: 50px;
            color: rgb(222,32,22);
            text-align: center;
        }
        
    /* h2 for categories */
        h2{
            font-family:verdana;
            font-size: 20px;
            color: rgb(222,32,22);
            text-align: left;
        }
</style>
    
    <h1>PALADIN</h1>

{#await loadSpells()}
<p>Loading...</p>
{:then spells} 
<pre>
    <h2>SPELLS</h2>

   <select bind:value = {selectedSpell} on:change={selectionChanged}>
       {#each spells.results as result} 
       <option value={result.index}>{result.name}</option> 
    {/each} 
   </select>
   </pre>
{/await}
{selectedSpell}