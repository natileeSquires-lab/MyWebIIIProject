<!-- Main Page -->
<script>
// import Data from other routes
    import Barbarian from './Barbarian.svelte';
    import Bard from './Bard.svelte';
    import Cleric from './Cleric.svelte';
    import Druid from './Druid.svelte';
    import Fighter from './Fighter.svelte';
    import Monk from './Monk.svelte';
    import Paladin from './Paladin.svelte';
    import Ranger from './Ranger.svelte';
    import Rogue from './Rogue.svelte';
    import Sorcerer from './Sorcerer.svelte';
    import Warlock from './Warlock.svelte';
    import Wizard from './Wizard.svelte';

// variables
    let selectedRadio = ' ';


// function for radio buttons
    function onChange(event) {
        selectedRadio = event.currentTarget.value;
    }

</script>

<style>

    /*global background for all routes*/
/*:global(body){
    min-height:100vh; 
    background-image: url("/img/background.jpg");
    background-repeat: no-repeat;
    background-size: 100% 100%;
    }   
    */  

</style>


    <button> 
    <!-- <p> <img src="img/cartoon.png" alt="Cartoon" width="50 px" height="50 px" style="vertical-align:middle"/> -->
        <label>
            <input checked={selectedRadio===10} on:change={onChange} type="radio" name="amount" value="10" /> Barbarian
        </label>
        <label>
            <input checked={selectedRadio===15} on:change={onChange} type="radio" name="amount" value="15" /> Bard
        </label>
        <label>
            <input checked={selectedRadio===20} on:change={onChange} type="radio" name="amount" value="20" /> Cleric
        </label>
        <label>
            <input checked={selectedRadio===25} on:change={onChange} type="radio" name="amount" value="25" /> Druid
        </label>
        <label>
            <input checked={selectedRadio===30} on:change={onChange} type="radio" name="amount" value="30" /> Fighter
        </label>
        <label>
            <input checked={selectedRadio===35} on:change={onChange} type="radio" name="amount" value="35" /> Monk
        </label>
        <label>
            <input checked={selectedRadio===40} on:change={onChange} type="radio" name="amount" value="40" /> Paladin
        </label>
        <label>
            <input checked={selectedRadio===45} on:change={onChange} type="radio" name="amount" value="45" /> Ranger
        </label>
        <label>
            <input checked={selectedRadio===50} on:change={onChange} type="radio" name="amount" value="50" /> Rogue
        </label>
        <label>
            <input checked={selectedRadio===55} on:change={onChange} type="radio" name="amount" value="55" /> Sorcerer
        </label>
        <label>
            <input checked={selectedRadio===60} on:change={onChange} type="radio" name="amount" value="60" /> Warlock
        </label>
        <label>
            <input checked={selectedRadio===65} on:change={onChange} type="radio" name="amount" value="65" /> Wizard
        </label>
        <label>
            <input checked={selectedRadio===70} on:change={onChange} type="radio" name="amount" value="70" /> Clear
        </label>
    </button>


<!-- Result of Radio Button selection -->
    {#if selectedRadio==="10"}
        <Barbarian/>
    {/if}
    {#if selectedRadio==="15"}
        <Bard/>
    {/if}
    {#if selectedRadio==="20"}
        <Cleric/>
    {/if}
    {#if selectedRadio==="25"}
        <Druid/>
     {/if}
     {#if selectedRadio==="30"}
        <Fighter/>
    {/if}
    {#if selectedRadio==="35"}
        <Monk/>
    {/if}
    {#if selectedRadio==="40"}
        <Paladin/>
    {/if}
    {#if selectedRadio==="45"}
        <Ranger/>
    {/if}
    {#if selectedRadio==="50"}
        <Rogue/>
    {/if}
    {#if selectedRadio==="55"}
        <Sorcerer/>
    {/if}
    {#if selectedRadio==="60"}
        <Warlock/>
    {/if}
    {#if selectedRadio==="65"}
    <Wizard/>
    {/if}