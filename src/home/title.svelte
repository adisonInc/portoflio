
<script>

   
    import { fade, fly } from 'svelte/transition';
    
   function typewriter(node, { speed = 1 }) {
		const valid = (
			node.childNodes.length === 1 &&
			node.childNodes[0].nodeType === Node.TEXT_NODE
		);

		if (!valid) {
			throw new Error(`This transition only works on elements with a single text node child`);
		}

		const text = node.textContent;
		const duration = text.length / (speed * 0.01);

		return {
			duration,
			tick: t => {
				const i = Math.trunc(text.length * t);
				node.textContent = text.slice(0, i);
			}
		};
    }

</script>

<div id="kox" transition:fade="{{duration: 1000 }}" >
   
    
    
        <h1 in:fly="{{ y: 200, duration: 1500 }}">Kamil</h1>
        <h1 in:fly="{{ y: -200, duration: 1500 }}">Plakwicz</h1>
   
</div>

<style>
    h1{
        text-transform: uppercase;
        color: #3c00f1;
        text-decoration:line-through;
        line-height: 2px;
        margin-left: 0;
        padding-left: 0;
    }   
    
    #kox{
       
        position: absolute;
        top: 20vh;
        left: 4vw;
        font-size: 5vh;
    }
      /*  animation: text-clip 1s 0s cubic-bezier(0.5, 0, 0.1, 1) both;
    }

    @keyframes text-clip {
        from {
            clip-path: polygon(0% 100%, 100% 100%, 100% 100%, 0% 100%);
        }
        to {
            clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
        }
}
*/
</style>
