<script>
    
    import { createEventDispatcher } from "svelte";
    import  GenericButton  from "./GenericButton.svelte";
    import Pokedex from "./Pokedex.svelte";

    let valorInput = "";
    $: Statushttp = null;

    const dispatcher = createEventDispatcher();

     async function loadPokemon()
    {
	    const pokemon = await getPokemon(valorInput.toLowerCase());
      
      if (pokemon === null){
        Statushttp = 404;
        dispatcher("getPokemon", null);
        alert('Pokémon não localizado.');
      } else {
        dispatcher("getPokemon", pokemon);
        Statushttp = null;
        
      }    
      
    }

</script>

<div class="busca-pokemon">
    <form on:submit|preventDefault={loadPokemon}>
      <Pokedex />
      <input
        type="text"
        class="input"
        class:erro-input={Statushttp === 404}
        bind:value={valorInput}
        placeholder="Pesquise aqui o Pokémon"
      />
  
      <GenericButton on:click={loadPokemon}>
        Buscar
        <img src="/assets/lupa.svg" alt="lupa" />
      </GenericButton>
    </form>
  </div>
  
  <style>
    .busca-pokemon {
      position: relative;      
      width: 100%; 
      align-items: center;     
    }
  
    .input {
      position: absolute;
      padding: 15px 25px;
      width: calc(100% - 8.75rem);
      font-size: 1rem;
      border-radius: 8px;
      border: 1px solid #2e80fa;
      box-shadow: 0px 17px 52px rgba(222, 231, 247, 0.4);
      outline: 0;
      left: 40px;      
    }
  
    .erro { 
      display: flex;
      margin-top: 100px;
      bottom: -25px;      
      font-style: italic;
      font-weight: normal;
      font-size: 16px;
      line-height: 19px;
      z-index: -1;
      color: #ff003e;
      background-color: aliceblue;
    }
  
    .erro-input {
      border: 1px solid #ff003e;
    }
  
    .input::placeholder {
      font-family: "Roboto";
      font-style: italic;
      font-weight: 300;
      font-size: 19.5px;
      line-height: 26px;
      color: #6e8cba;
    }
  </style>
  