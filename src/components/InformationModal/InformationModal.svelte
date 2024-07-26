<script lang="ts">
	import Overlay from '../Commons/Overlay.svelte';
	import clickOutside from '../../action/clickOutside';
	import { slide } from 'svelte/transition';

	export let display: boolean = false;
</script>

<Overlay>
	{#if display}
		<div id="background"></div>
		<main transition:slide use:clickOutside={() => display = false} id="informationModal">
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
					<slot name="content"></slot>
				</main>
			</div>
		</main>
	{/if}

</Overlay>

<style lang="scss">
	@import "../../../static/variables";
  #background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.5);
    z-index: 1;
  }

  main#informationModal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    border-radius: 10px;
    z-index: 2;

    div {
      width: 80vw;
      display: flex;
      flex-direction: column;
      justify-content: center;
      @media only screen and (min-width: $xl) {
        width: 25vw;
      }

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
