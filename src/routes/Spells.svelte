<script>

    let selectedClass;
    let selectedSpell;
   //  let spells;

//function to list classes for drop down
    async function loadClasses(searchQuery=""){
         const response = await fetch(`https://www.dnd5eapi.co/api/classes/${searchQuery}?format=j1`);
        const result = await response.json(); 
        return result;
    }

    async function loadSpells(searchQuery=""){
        const response = await fetch(`https://www.dnd5eapi.co/api/classes/${selectedClass}/spells/${searchQuery}?format=j1`);
       const result = await response.json(); 
       return result;
   }

   async function loadWeather(searchQuery=""){
        const response = await fetch(`https://www.dnd5eapi.co/api/spells/${selectedSpell}/${searchQuery}?format=j1`);
      //  const response = await fetch(`https://www.dnd5eapi.co/api/spells/${selectedSpell}/${searchQuery}?format=j1`);
       const result = await response.json(); 
       return result;
   }

   // function to select class
   function selectionChanged(event){
         if(!event.target.value) return;
     }

</script>

<style>

   /*global background for all routes*/
:global(body){
   min-height:100vh; 
   background-image: url("/img/background.jpg");
   background-repeat: no-repeat;
   background-size: 100% 100%;
   }     

</style>

{#await loadClasses()}
    <p>Loading...</p>
{:then classes} 
<pre>
   <!-- {JSON.stringify(classes,false,2)} -->
   <!-- {classes.results[3].name } -->

   <select bind:value = {selectedClass} on:change={selectionChanged}>
       {#each classes.results as result} 
       <option value={result.index}>{result.name}</option> 
    {/each} 
   </select>
       
</pre> 
{/await} 

  <!--If statement to use spells from barbarian class  -->
  {#if selectedClass ==="barbarian"}
  {#await loadSpells()}
  <p>Loading...</p>
 {:then spells} 
 <pre>
     <select bind:value = {selectedSpell} on:change={selectionChanged}>
         {#each spells.results as result} 
         <option value={result.index}>{result.name}</option> 
      {/each} 
     </select>
     </pre>
 {/await}
{selectedSpell}
  {/if}

  <!--If statement to use spells from bard class  -->
  {#if selectedClass ==="bard"}
  {#await loadSpells()}
  <p>Loading...</p>
 {:then spells} 
 <pre>
     <select bind:value = {selectedSpell} on:change={selectionChanged}>
         {#each spells.results as result} 
         <option value={result.index}>{result.name}</option> 
      {/each} 
     </select>
     </pre>
 {/await}
{selectedSpell}
  {/if}

     <!--If statement to use spells from cleric class  -->
     {#if selectedClass ==="cleric"}
     {#await loadSpells()}
     <p>Loading...</p>
    {:then spells} 
    <pre>
        <select bind:value = {selectedSpell} on:change={selectionChanged}>
            {#each spells.results as result} 
            <option value={result.index}>{result.name}</option> 
         {/each} 
        </select>
        </pre>
    {/await}
{selectedSpell}
     {/if}

     <!--If statement to use spells from druid class  -->
     {#if selectedClass ==="druid"}
     {#await loadSpells()}
     <p>Loading...</p>
    {:then spells} 
    <pre>
        <select bind:value = {selectedSpell} on:change={selectionChanged}>
            {#each spells.results as result} 
            <option value={result.index}>{result.name}</option> 
         {/each} 
        </select>
        </pre>
    {/await}
{selectedSpell}

    {#await loadWeather()}
    <p>Loading...</p>
 {:then weather}
 <pre>
     {JSON.stringify(weather,false,2)}
 </pre> 
 {/await} 
     {/if}

           <!--If statement to use spells from fighter class  -->
           {#if selectedClass ==="fighter"}
           {#await loadSpells()}
           <p>Loading...</p>
          {:then spells} 
          <pre>
              <select bind:value = {selectedSpell} on:change={selectionChanged}>
                  {#each spells.results as result} 
                  <option value={result.index}>{result.name}</option> 
               {/each} 
              </select>
              </pre>
          {/await}
{selectedSpell}
           {/if}

     <!--If statement to use spells from monk class  -->
     {#if selectedClass ==="monk"}
     {#await loadSpells()}
     <p>Loading...</p>
    {:then spells} 
    <pre>
        <select bind:value = {selectedSpell} on:change={selectionChanged}>
            {#each spells.results as result} 
            <option value={result.index}>{result.name}</option> 
         {/each} 
        </select>
        </pre>
    {/await}
{selectedSpell}
     {/if}

 <!--If statement to use spells from paladin class  -->
 {#if selectedClass ==="paladin"}
{#await loadSpells()}
<p>Loading...</p>
{:then spells} 
<pre>
   <select bind:value = {selectedSpell} on:change={selectionChanged}>
       {#each spells.results as result} 
       <option value={result.index}>{result.name}</option> 
    {/each} 
   </select>
   </pre>
{/await}
{selectedSpell}
{/if}

     <!--If statement to use spells from ranger class  -->
     {#if selectedClass ==="ranger"}
     {#await loadSpells()}
     <p>Loading...</p>
    {:then spells} 
    <pre>
        <select bind:value = {selectedSpell} on:change={selectionChanged}>
            {#each spells.results as result} 
            <option value={result.index}>{result.name}</option> 
         {/each} 
        </select>
        </pre>
    {/await}
{selectedSpell}
     {/if}

     <!--If statement to use spells from rogue class  -->
     {#if selectedClass ==="rogue"}
     {#await loadSpells()}
     <p>Loading...</p>
    {:then spells} 
    <pre>
        <select bind:value = {selectedSpell} on:change={selectionChanged}>
            {#each spells.results as result} 
            <option value={result.index}>{result.name}</option> 
         {/each} 
        </select>
        </pre>
    {/await}
{selectedSpell}
     {/if}

     <!--If statement to use spells from sorcerer class  -->
     {#if selectedClass ==="sorcerer"}
     {#await loadSpells()}
     <p>Loading...</p>
    {:then spells} 
    <pre>
        <select bind:value = {selectedSpell} on:change={selectionChanged}>
            {#each spells.results as result} 
            <option value={result.index}>{result.name}</option> 
         {/each} 
        </select>
        </pre>
    {/await}
{selectedSpell}
     {/if}

     <!--If statement to use spells from warlock class  -->
     {#if selectedClass ==="warlock"}
     {#await loadSpells()}
     <p>Loading...</p>
    {:then spells} 
    <pre>
        <select bind:value = {selectedSpell} on:change={selectionChanged}>
            {#each spells.results as result} 
            <option value={result.index}>{result.name}</option> 
         {/each} 
        </select>
        </pre>
    {/await}
{selectedSpell}
     {/if}

  <!--If statement to use spells from wizard class  -->
  {#if selectedClass ==="wizard"}
  {#await loadSpells()}
  <p>Loading...</p>
 {:then spells} 
 <pre>
     <select bind:value = {selectedSpell} on:change={selectionChanged}>
         {#each spells.results as result} 
         <option value={result.index}>{result.name}</option> 
      {/each} 
     </select>
     </pre>
 {/await}
{selectedSpell}
  {/if}
