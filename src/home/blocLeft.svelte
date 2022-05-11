<script>
    export let text;
    export let imgsrc;
    export let imgalt
    import { doned } from '../init/done.js'
</script>
{#if $doned == true}
<div id="cbdiv">
    <img src={imgsrc} alt={imgalt}>
    <div id="text"><span id="sp">{@html text}</span></div>
    <div id="tri"></div>
</div>
{/if}


<style>
    #cbdiv{
        
        height: 40vh;
        margin-top: 40vh;
        margin-left: 4vw;
        display: flex;
        flex-direction: row;
        animation: text-clip 2.5s 0s cubic-bezier(0.5, 0, 0.1, 1) both;
    }
    
    @keyframes text-clip {
        from {
            clip-path: polygon(0% 100%, 100% 100%, 100% 100%, 0% 100%);
        }
        to {
            clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
        }
    }
    img{
        
        height: 30vh;
        
        filter: sepia() hue-rotate(160deg) grayscale(50%) ;
        grid-row-start: 1;
        
      
        color: transparent;
        left: 4vw;

        
    }
    #text{
        position: relative;
        font-size: 5vw;
        color: whitesmoke;
        
        width: 50vw;
        height: 30vh;
        z-index: 31;  
        line-height: 4vw; 
        white-space: pre-line;
       
    }

    #sp{
        position: absolute;
        bottom: 0;
        left: 0;
    }

    #tri {
      position: absolute;
	  left: 15vw;
	  top: 30vh;
	  z-index: -1;
      width: 0;
      height: 0;
      border-bottom: 24vw solid #190061;
      border-left: 30vw solid transparent;
    }


</style>