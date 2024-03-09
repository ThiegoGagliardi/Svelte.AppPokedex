<script>
    import PokemonStatus from "./PokemonStatus.svelte";

   export let pokemon;
    
</script>

<div class="detailPokemon {pokemon.type}" id="{pokemon.name}">
           
    <div class="apresentacao">              
         <div class = "NameNumber">
             <span class="name">{pokemon.name}</span>
             <span class="number">{pokemon.number}</span>
         </div>                
         <div>
             <ul class="types">
                  {#each pokemon.types as type}
                     <li class="type {type}">{type}</li>
                  {/each}
             </ul>                    
         </div>
         <div class="pokeimg"> 
             <img src="{pokemon.img}" alt="{pokemon.name}"> 
         </div>
      
        <PokemonStatus {pokemon} />
    </div>                             
 </div>
 
 <style>


.hide{
    display: none;  
}

.disable li{
    opacity: .6;  
}

.number {
    color: #000;
    opacity: .3;
    text-align: right;
    font-size: .625rem;
}

.name {
    text-transform: capitalize;
    color: #fff;
    margin-bottom: .25rem;
}

.detail {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}

.types {
    padding: 0;
    margin: 0;
    list-style: none;
}

.type {
    color: #fff;
    padding: .25rem .5rem;
    margin: .25rem 0;
    font-size: .625rem;
    border-radius: 1rem;
    filter: brightness(1.1);
    text-align: center;
}

.pokeimg {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: auto;
  margin-right: auto;  
}

.img {
    margin-left: auto;
    margin-right: auto;
    display: block;
}

.PokemonData{
    display: flex;
    flex-direction: row;
    width: auto;
}

.detailPokemon {
    display: flex;
    flex-direction: column;
    margin: .5rem;
    padding: 1rem;
    border-radius: 1rem;
    align-items: center; 
    height: max-content;
    list-style: none;
    width: 100%;        
}

.apresentacao {
    display: flex;
    flex-direction: column;
    margin: .5rem;
    padding: 1rem;
    border-radius: 1rem;
}

.NameNumber{
    display: flex;
    flex-direction: row;
    align-content: space-between;
    align-items: center;
    text-align: justify;
}

 .number {
    color: #000;
    opacity: .6;
    text-align: right;
    width: 50%;
}

.detailPokemon .apresentacao .NameNumber .name {
    text-transform: capitalize;
    text-align: left;
    color: #fff;
    margin-bottom: .25rem;
    width: 50%;
}

.detailPokemon .apresentacao .types {
    padding: 0;
    margin: 0;
    list-style: none;
}

.detailPokemon .apresentacao .types .type {
    color: #fff;
    padding: .25rem .5rem;
    margin: .25rem 0;
    font-size: .625rem;
    border-radius: 1rem;
    filter: brightness(1.1);
    text-align: center;
}

.detailPokemon .apresentacao .NomeOrdem{    
    justify-content: space-between;
    color: #fff;
    text-transform: capitalize;    
    margin-bottom: .25rem;   
}

.detailPokemon .apresentacao img {
    max-width: 100%;
    height: 100px;
}

.detailPokemon .status {
    max-width: 100%;       
    background-color: #fff;
    height: 100%;
    width: 100%;
    border-radius: 1rem;       
    color: #000;
    padding: 10px;
    display: flex;
    flex-direction: row;
}

@media screen and (min-width: 380px) {
    .pokemons {
        grid-template-columns: 1fr 1fr;
    }
}

@media screen and (min-width: 576px) {
    .pokemons {
        grid-template-columns: 1fr 1fr 1fr;
    }
}

@media screen and (min-width: 992px) {
    .pokemons {
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
}

@media screen and (min-width: 380px) {
    .detailPokemon {
        grid-template-columns: 1fr 1fr;
    }
}

@media screen and (min-width: 576px) {
    .detailPokemon {
        grid-template-columns: 1fr 1fr 1fr;
    }
}

@media screen and (min-width: 992px) {
    .detailPokemon {
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
}
 </style>