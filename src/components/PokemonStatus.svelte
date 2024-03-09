<script>
    export let pokemon;
</script>

<div class="status">            
    <div class="sobre">
        <label class="title">Altura:</label><label class="total">{pokemon.altura}</label><br>
        <label class="title">Peso:</label><label class="total">{pokemon.peso}</label><br>
        <label class="title">Habilidades:</label>                    
        {#each pokemon.habilidades as habilidade}
            <label class="habilidade {pokemon.type}">{habilidade}</label><br>
        {/each}      
    </div>               
    <div class="statusbase">
        {#each pokemon.Status as status} 
        <label class="title"> {status.name}:</label>
        <label class="total">{status.total}</label> 
        <br>
        {/each}
    </div>    
</div> 

<style>

.status {
    max-width: 100%;       
    min-width: 100%;
    background-color: #fff;
    height: 100%;    
    border-radius: 1rem;       
    color: #000;
    padding: 10px;
    display: flex;
    flex-direction: row;
}

.statusbase{
    max-width: 100%;       
    background-color: #fff;
    height: 100%;
    width: 100%;
    border-radius: 1rem;
    display: grid;    
    color: #000;
    padding: 10px;    
    flex-direction: row;    
    align-content: space-between;
}

.sobre{
    max-width: 90%;       
    background-color: #fff;
    height: 100%;
    width: 50%;
    border-radius: 1rem;
    display: grid;    
    color: #000;
    padding: 10px;    
    flex-direction: column;
    align-content: space-between;
}

.habilidade {
    color: #fff;
    padding: .25rem .5rem;
    margin: .25rem 0;
    font-size: .625rem;
    border-radius: 1rem;
    filter: brightness(1.1);
    text-align: center;
} 

.habilidades{
    list-style: none;
}

.title {
  opacity: 0.7;
}

.total {
  color : green;
}
</style>
 