<script>


    import { fade, blur, fly, slide, scale } from "svelte/transition";

    export let txt;
    export let which;
   
    let translate;
    let hover;
    let bar;


     let logos = ["images/logo/flutter.png",
    "images/logo/Svelte.png",
    "images/logo/js.png",
    "images/logo/pytho.png",
    "images/logo/go.png"]


    let desc = ["Flutter: Zrobiłem pare aplikacji np. Trukzzz, Vibe Checker która była na konkurs",
                "Svelte: Ta strona jest napisana w tym frameworku",
                "JavaScript: Zarówno vanilla jak i próbowałem dużo frameworków takich jak React, Vue.js",
                "Python: Dużo pojedyńczych programów które automatyuzują różne rzeczy webdriver, pyGame,Tkinter i tego typu",
                "Go: Używam go gdy pracuje z dużymi plikami oraz gdy podtrzebuje szybkiego języka"]

    import Lvl from "./lvl.svelte"

  
  
   function handleHover(){
        hover = true;
        switch (which) {
        case logos[0]:
            translate = desc[0];
            bar = 0.7
            break;
        case logos[1]:
            translate = desc[1];
            bar = 0.3
            break;
        case logos[2]:
            translate = desc[2];
            bar = 0.4
            break;
        case logos[3]:
            translate = desc[3];
            bar = 0.8
            break;
        case logos[4]:
            translate = desc[4];
            bar = 0.4
            break;
        default:
            break;
    }
    }

    function unhandleHover(){
        hover = false;
    }
    
    

</script>


<div class="box">
{#if hover == true}
<div class="flex">
    <div in:fly="{{ x: -200, duration: 1000 }}" out:fly="{{ x: 200, duration: 1000 }}" class="cloud">
        <p>{translate}</p>
        <div id="bar">
            <p> Poziom Znajomości</p>
            <Lvl id="bar" prog={bar}></Lvl>
        </div>
    </div>
</div>
{/if}
<img on:mouseover={handleHover} on:mouseleave={unhandleHover} class="imgs" src={which} alt="logo">
</div>
<style>

    .flex{
        position: absolute;
        width: 100vw;
        height: 10vh;
        display: grid;
        place-items: center;


    }

    p{
        color: white;
    }

    .box{
        left: -10vw;

    }

    #bar{
        position: absolute;
        bottom: 1vh;
        display: grid;
        place-items: center;

    }
    .cloud{
        left: -3vw;
        position: absolute;
        padding: 4vw;
        width: 20vw;
        bottom: 10vh;
        z-index: 10;

        background-color: #3500D3;
        border-radius: 26px;

        display: grid;
        place-items: center;

        
        

    }

    .imgs{

       

        margin: 1vw;

        padding: 0;
        height: 10vw;
        filter: sepia() hue-rotate(160deg) grayscale(30%);
        /* animation-name: srcoll;
        animation-direction: alternate;
        animation-iteration-count: infinite;
        animation-duration: 3s; */

    }

    .imgs:hover{
        animation: koxu 3s  infinite ;
    }

   
    

    @keyframes koxu{
        0% {filter: sepia() hue-rotate(160deg) grayscale(30%); }
        
        100% { filter: sepia(50%)  grayscale(15%);}
       
        /* 100% {filter:  grayscale(0%); } */
    }
</style>