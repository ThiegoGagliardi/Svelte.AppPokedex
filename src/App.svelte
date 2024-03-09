<script>
	import Title from "./components/Title.svelte";
	import BarraBusca from "./components/BarraBusca.svelte";
	import PokemonCard from "./components/PokemonCard.svelte";

	let pokemon = null;

	function getPokemon(event){

		pokemon = event.detail;
  	} 	
</script>

<div class="main" >
	<Title />
	
	<BarraBusca on:getPokemon={getPokemon} />
	
	<div class="pokemon">
		{#if pokemon}
			<PokemonCard {pokemon} />
		{/if}
    </div>	
</div>

<style>

.main{
	background-image: url("/assets/background.jpg");
	background-size: 100px;
	background-repeat: space;

	width : 100%;
	height: 120%;

	justify-content: center;
}

.pokemon {

    display: flex;
	flex-direction: column;    
    padding: 1rem;
    border-radius: 1rem;
	border: 2px black;
    overflow: hidden;
	max-width: 40%;
	align-items: center;
	margin: auto;
	margin-top: 40px;
}
</style>