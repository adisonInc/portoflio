<script>

    import SButton from "./buttons.svelte"
    import { fade } from 'svelte/transition';
    import { quintOut } from 'svelte/easing';
    import { doned } from './done';
    let dots = [".","..","..."]
    $: x = 0;
    $: prgrs = 0;
    let click = false;
    

    async function sleeper(seconds){
		return new Promise((resolve) => setTimeout(resolve,seconds * 1000))
	} 

    
    

    async function strt(){
        click = true;
        while(prgrs <= 100){ 
          await sleeper(0.01);
          prgrs = prgrs + 1;
          if(prgrs % 15 == 0){
              x = x + 1;
              if( x == 3){
                  x = 0
                }
            
          }
          
        } 
        doned.set(true)       
    }

</script>



{#if $doned == false}
<div transition:fade="{{duration: 500 }}" id="kox" >
    <div id="box"  style="--theme-color:{prgrs};">
        {#if click == true}
        <div id="cap">
        
            <h1 id="static">Loading</h1> 
            <div id="bcap">    
                <h1>{dots[x]}</h1>
            </div> 
            
        </div>
        <div id="bar">
            <div id="progress">
                {#if prgrs > 100 }
                <p id="cnt">{prgrs}%<p>
                {/if}
            </div>
            
            
        </div>
        {/if}
        {#if click == false}
            <SButton cont="Start" func={strt} ></SButton>
        {/if}
    </div>
</div>
{/if}

<style>
    #box{
        width: 50vw;
        height: 25vh;
        
        display: grid;
        place-items: center;
    }

    #bar{
        border: 3px;
        border-color: red;
        background-color: #190061 ;
        width: 30vw;
        height: 10vh;
       
   }
    
   #progress{
       position: relative;
       height: 10vh;
       width: calc(var(--theme-color)* 1%);
       
       background-color: #3500D3;
     
      
      
   }

   #cap{
      display: flex;
      flex-direction: row;  
      
         

   }
   #bcap{
       display: flex;
       flex-direction: row;
    
        width: 0.0001px;
   }
   #static{
       margin-right: 0.2vw;
   }
   h1{
       color: whitesmoke;
   }
   #kox{
        
       position: absolute;
         
       width: 100vw;
       height: 100vh;
       margin: 0;
        padding: 0;
       
       background-color: black;
       z-index: 999;
       display: grid;
       place-items: center;
       
   }
   #progress{
       display: grid;
       place-items: end;
   }
   #cnt{
       font-size: 1vw;
       position: absolute;
       right: 0;
       top: 50%;
       color: whitesmoke;
   }

   
</style>