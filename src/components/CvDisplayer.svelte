<script lang="ts">
	import { slide } from 'svelte/transition';
	import Overlay from './Commons/Overlay.svelte';
	const pathToPdf = './cv/cv.pdf#navpanes=0&scrollbar=0statusbar=0&messages=0&scrollbar=0&zoom=75';
	import clickOutside from '../action/clickOutside';
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';

	export let display: boolean = false;

	let height = 0
	let width = 0

	onMount(() => {
		if(!browser) return
		function handleResize() {
			height = window.innerHeight - 100;
			width = height * 0.7;
		}
		handleResize()
		window.addEventListener('resize', handleResize)

		return () => window.removeEventListener('resize', handleResize)
	})
</script>


<Overlay>
	{#if display}
		<div id="background"></div>
		<main transition:slide use:clickOutside={() => display = false} id="cvDisplayer">
			<div>
				<header>
					<slot name="title"></slot>
					<button on:click={() => display = false}>
						<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"  fill="#ccc">
							<path
								d="M12 10.586l-4.293-4.293-1.414 1.414 4.293 4.293-4.293 4.293 1.414 1.414 4.293-4.293 4.293 4.293 1.414-1.414-4.293-4.293 4.293-4.293-1.414-1.414z" />
						</svg>
					</button>
				</header>
				<main>
						<iframe src={pathToPdf} {width} {height} title="nicolas-devos-cv"></iframe>
				</main>
			</div>
		</main>
	{/if}

</Overlay>


<style lang="scss">
  @import "../../static/variables";
  #background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.5);
    z-index: 1;
  }

  main#cvDisplayer {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    border-radius: 10px;
    z-index: 2;

    div {
      display: flex;
      flex-direction: column;
      justify-content: center;

      header {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        padding: 5px 20px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);

        button {
          background: none;
          border: none;
          cursor: pointer;
        }
      }


      main {
        padding: 20px;
      }
    }
  }

</style>
