<script>
    
    let logos = ["images/logo/flutter.png",
    "images/logo/Svelte.png",
    "images/logo/js.png",
    "images/logo/pytho.png",
    "images/logo/go.png"]

   
    $: hover = false;
    import Cloud from "./hover.svelte"
    import Images from "./hover.svelte"
    function handleHover(){
        hover = true;
    }

    function unhandleHover(){
        hover = false;
    }

</script>

<div class="flex">
    <p id="title">Technologie których używam</p>
    <div id="roll">
        
        {#each logos as kox}
            <Images which={kox} txt={kox}></Images>
            <!-- <img on:mouseover={handleHover} on:mouseleave={unhandleHover} class="imgs" src={kox} alt="logo"> -->
            <!-- {#if hover == true} -->
                
            <!-- {/if} -->
            
        {/each}
        <!-- <Cloud txt="{kox}"></Cloud> -->
        <!-- {#each logos as kox} -->
            <!-- <img class="imgs" src={kox} alt="logo"> -->
        <!-- {/each} -->
    </div>
</div>

<style>
    

    p{
        color: #3c00f1;
        /* color: white */
    }

    .flex{

        max-width:100%; 
        width: 10vw;
        height: 10vh;
        margin: 0;
  	    padding: 0;
        margin-top: 4vh;
        display: grid;
        place-items: center;



        /* margin: auto;
        height: 10vh;
	    margin: auto;
	   overflow:hidden;
	   position: relative;
	   width: 100vw; */
    }
    

    #title{
        font-size: 8vh;
    }
    #roll{
        max-width:100%; 
        width: 100vw;
        height: 12vw; 
        padding: 3vh;


        background-color: #190061;
        /* background-color: white;; */
        display: flex;
        
        /* grid-template-rows: 1fr; */
        /* grid-template-columns: 1fr 1fr 1fr; */

        flex-direction: row;
        justify-content:space-around;

        /* animation: scroll 3s linear infinite; */
		/* display: flex; */
		/* width: calc(250px * 14); */
    }

  


</style>