<script lang="ts">
	import { onMount } from 'svelte';
	import NavMenu from '../Nav/NavMenu.svelte';
	import BurgerButton from './BurgerButton.svelte';
	import Logo from './Logo.svelte';
	import ContactModal from '../ContactModal/ContactModal.svelte';
	import { base } from '$app/paths';

	let scrollPosition: number = 0;
	let displayContactModal: boolean = false;

	onMount(() => {
		console.log('Header mounted');
		window.addEventListener('scroll', () => {
			scrollPosition = window.scrollY;
		});
	});
	let showMenu: boolean = false;

</script>

<header id="navBar" class:opacity={scrollPosition > 0}>
	<main>
		<div id="my-name" class:black={scrollPosition > 0}>
			<p>
				Nicolas Devos
			</p>
		</div>
		<span class="burgerIcon">
				{#if scrollPosition > 0}
				<BurgerButton stroke="black" on:click={()=>{showMenu= !showMenu}} />
							{:else}
				<BurgerButton stroke="white" on:click={()=>{showMenu= !showMenu}} />
				{/if}
		</span>
		<div class="links">
			<a href="#projects">Projets</a>
			<button on:click|preventDefault|stopPropagation={()=>{displayContactModal = true}}>Contact</button>
			<a href="{base}/cv">Cv</a>
		</div>
	</main>
	<NavMenu display={showMenu} class="links">
		<a href="#projects">Projets</a>
		<button on:click|preventDefault|stopPropagation={()=>{displayContactModal = true}}>Contact</button>
		<a href="{base}/cv">Cv</a>
	</NavMenu>
</header>
<ContactModal bind:display={displayContactModal}></ContactModal>
<style lang="scss">
  @import '../../../static/variables';

  .burgerIcon {
    display: none;
    @media only screen and (max-width: $lg) {
      display: block;
    }
  }


  header {
    position: fixed;
    width: 100%;
    top: 0;
    background-color: transparent;
    z-index: 5;
    max-height: fit-content;
    transition: all 0.5s;

    @media only screen and (max-width: $xl) {
      background-color: var(--color-primary);
    }

    &.opacity {
      background-color: white;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);

      #logo {
        opacity: 1;
      }

      .links {

        a, button {
          color: black;
        }

      }
    }

    main {
      display: flex;
      flex-direction: row;
      padding: 20px;
      justify-content: space-between;
      align-items: center;

    	#my-name {

        p {
        color: white;
          font-size: 1.5rem;
          font-weight: 500;
          margin: 0;

        }

        &.black {
          p {

            color: black;
          }
        }

        @media only screen and (min-width: $xl) {
          opacity: 0;

        }
      }

    }


    .links {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-end;
      gap: 20px;

      button {
        background: transparent;
        border: none;
        cursor: pointer;
        margin: 0 !important;
        padding: 0 !important;
      }

      @media only screen and (max-width: $lg) {
        display: none;
      }

      a, button {
        color: white;
        text-decoration: none;
        font-size: clamp(1rem, 2vw, 1.5rem);
        font-weight: 500;
        transition: color 0.5s;

        &:hover {
          color: var(--color-tertiary);
        }
      }
    }
  }

</style>
