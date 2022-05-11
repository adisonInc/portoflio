<script>
    export let text;
    export let imgsrc;
    export let imgalt
</script>

<div id="cbdiv">
    <img src={imgsrc} alt={imgalt}>
    <div id="text">{text}</div>
</div>


<style>
    #cbdiv{
        position: absolute;
        width: 30vw;
        height: 40vh;
       
        margin-top: 8vw;
        right: 2vw;
        display: grid;
    }
    img{
        position: absolute;
        height: 30vh;
        filter:sepia();
        filter: hue-rotate(blue);
        grid-row-start: 1;
        grid-column-start: 1;
        background-clip: text;
        -webkit-background-clip: text;
        color: transparent;

        
    }
    #text{
        position: absolute;
        color: #240090;
      
        width: 25vw;
        height: 10vh;
        z-index: 31; 
        margin-top: 5vw;
        right: 15vw;
    }
</style>