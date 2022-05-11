<script>
	import Top from "./Top.svelte";
	import { doned } from './init/done';
	import LodaBar from "./init/lbar.svelte"
	import Bright from "./home/blocRight.svelte"
	import Bleft from "./home/blocLeft.svelte"
	import Title from "./home/title.svelte"
	import Proj from "./home/proj.svelte"



	let cbtext = "17 lat \n Geniusz \n Uczeń Technikum"
	import Tech from "./home/technologie.svelte"
	
	async function sleeper(seconds){
		return new Promise((resolve) => setTimeout(resolve,seconds * 1000))
	}
</script>
<head>
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
<main>
	<!-- <div id="first"> -->
		<LodaBar ></LodaBar>
		{#if  $doned == true}
			<Top></Top>
		
			<Title></Title>
		
		{/if}
		
		
		<Bleft imgalt="charles" imgsrc="images/cb.jpg" text="{cbtext}"></Bleft>
	<!-- </div> -->
	<!-- <div id="snd"	> -->
		<Tech></Tech>
		<Proj></Proj>

	<!-- </div> -->
	
</main>
</body>
<style>
	
	 
	/* #first{
		position: absolute;
		top: 0;
		background-color: black;
		width: 100vw;
		height: 100vh;
		margin: 0;
		padding: 0;
	}
	
	#snd{
		position: absolute;
		top: 100vh;
		background-color: #190061;
		width: 100vw;
		height: 100vh;
		margin: 0;
		padding: 0;
	} */

	:global(h1,h2,h3,h4,p){
		font-family: monospace;
	}


    

	:global(body) {
		overflow-x: hidden;
		margin: 0;
  	    padding: 0;
		background-color: black
		
		
	}

	@media (min-width: 640px) {
		main {

		
	
			max-width: 100vw;
			background-color: black;
			width: 100vw;
			
			position: absolute;
			z-index: 0;
			top: 0;
			left: 0;
			margin: auto 0;
		}
	}
</style>