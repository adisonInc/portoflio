<script>
    let proj = ["NetflixManager", "VibeTracker","Trukzz","SptLyr"]
    let nmbs = ["/2020","/2021","/2022"]
    let nmb;
    let hover = false;
   function handleBox(){
        hover = true;
       
    }


    function unhandleBox(){
        hover = false;
    }

</script>

<div class="box">
    <div class="vert">  <h1>MOJE PROJEKTTY</h1> </div>
   
    <div class="horz">
        {#each proj as prj}
        <div class="flex">
                {#if hover == false}
                <h2 id="proj" on:click={handleBox} >{prj}</h2><h4>/2022</h4>
                {/if}
               
        </div>
        {/each}
        {#if hover == true}
        <div class="flex"> <div class="boxix"> <p>Projekt na konkurs bla bla bla z kolegom robilem w 2 tygodnie ez Projekt na konkurs bla bla bla z kolegom robilem w 2 tygodnie ez Projekt na konkurs bla bla bla z kolegom robilem w 2 tygodnie ez Projekt na konkurs bla bla bla z kolegom robilem w 2 tygodnie ez</p></div>
        <h1 id="back" on:click={unhandleBox}>Wróc</h1>
        </div>
        {/if}
    </div>
</div>

<style>
    p{
        color: white;
        padding: 2vw;
    }


    #proj:hover{
        text-decoration: underline;
    }
    #back:hover{
        text-decoration: underline;
    }

    #back{
        margin-left: 1vw;

        -webkit-transform:rotate(-0deg);
        -moz-transform:rotate(90deg);
        -o-transform: rotate(90deg);
        -ms-transform:rotate(90deg);
        transform: rotate(90deg);
        
        white-space:nowrap;
        display:block;
        bottom:0;
        height: 20vh;
        width: 5vw;
    }

    /* #snd{ */
        /* margin-left: 50vh; */
    /* } */

    .boxix{
        width: 50vw !important;
        height: 30vw;
        background-color: #3c00f1;
    }

    @keyframes kox {

        to {margin-left: 30vh;}
    }

    .flex{
        display: flex;
        flex-direction: row;
        
    }

    .box{
        
        position: relative;
        margin-left: 5vw;
        height: 50vh;
        margin-top: 120vh;
        width: 100vw;
        display: flex;
        flex-direction: row;
    }
    
    .vert{
       
        font-size: 2vw;
        color: white;

        -webkit-transform:rotate(-90deg);
        -moz-transform:rotate(-90deg);
        -o-transform: rotate(-90deg);
        -ms-transform:rotate(-90deg);
        transform: rotate(-90deg);
        
        white-space:nowrap;
        display:block;
        bottom:0;
        height: 20vh;
        width: 5vw;

    }
    .horz{
        position:absolute;
        font-size: 1.5vw;
        width: 50vw;
        height: 10vh;
        color: white;
        top: -51vh;
        left: 10vw;
        
       
    }

</style>