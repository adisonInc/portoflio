
<script>
    import { fade, blur, fly, slide, scale } from "svelte/transition";
</script>

<div id="bar">
    
   
   
    <h3 in:fly="{{ x: -200, duration: 2000 }}" id="name" class="fixed">Kamil Plakwicz</h3>
    <h3 in:fly="{{ x: -500, duration: 3000 }}">Geniusz</h3>
    <h3 in:fly="{{ x: 500, duration: 3000 }}">Based in Bramka</h3>
    <h3 in:fly="{{ x: 200, duration: 2000 }}" id="links" class="fixed"><a href="https://github.com/adisonInc"  target="_blank">GitHub </a> & <a href="mailto: koxunio767@gmail.com">e-mail </a></h3>
</div>

<style>
    #bar{
        position: absolute;
        top: 0;
        left: 0;
        margin: 0 auto;   
        width: 100vw;
        height: 10vh;
  
        /* background-color: #0c0032 ; */
        flex-direction: row;
        justify-content: space-evenly;
        display: flex;
        
    } 
     img{
       height: 100%;
       margin-left: 2em;
       
   }

   h1{
       color: #3500D3;
       font-size: 8vh;
       margin-top: 1vh; 
       margin-left: 0.5em;
       
   }
   h3{
       color: #3500D3;
       
   }
   
   a:link{
       color: #3500D3;
   }
   a:visited {
        color: #3500D3;
    }

    a:hover {
        color: whitesmoke;
        text-decoration: none;
    }
    
    .fixed{
        z-index: 99;
        position: fixed;
    }
    
    #name{
        left: 5vw;
    }

    #links{
        right: 5vw;
    }

</style>