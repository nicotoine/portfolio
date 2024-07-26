<script lang="ts">
	import { onMount } from 'svelte';
	import NavMenu from '../Nav/NavMenu.svelte';
	import BurgerButton from './BurgerButton.svelte';
	import Logo from './Logo.svelte';

	let scrollPosition: number = 0;
	onMount(() => {
		console.log('Header mounted');
		window.addEventListener('scroll', () => {
			scrollPosition = window.scrollY;
		});
	});
	let showMenu: boolean = false;
</script>

<header class:opacity={scrollPosition > 0}>
	<main>
		<div id="logo">
			{#if scrollPosition > 0}
				<Logo fill="black" />
			{:else}
				<Logo fill="white"/>
			{/if}
		</div>
		<span class="burgerIcon">
				{#if scrollPosition > 0}
				<BurgerButton stroke="black" on:click={()=>{showMenu= !showMenu}} />
							{:else}
				<BurgerButton stroke="white" on:click={()=>{showMenu= !showMenu}} />
				{/if}
		</span>
		<div id="links">
			<a href="/me">A propos</a>
			<a href="/me">Projets</a>
			<a href="/me">Contact</a>
		</div>
	</main>
	<NavMenu display={showMenu}></NavMenu>
</header>

<style lang="scss">
  @import '../../../static/variables';

  .burgerIcon {
    display: none;
    @media only screen and (max-width: $sm) {
      display: block;
    }
  }

  header {
		position: sticky;
		top: 0;


		background-color: transparent;
    @media only screen and (max-width: $xl) {
			background-color: var(--color-primary);
    }

		z-index: 5;
    max-height: fit-content;
    transition: all 0.5s;

    &.opacity {
      background-color: white;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    }
    main {
      display: flex;
      flex-direction: row;
      padding: 20px;
      justify-content: space-between;
      align-items: center;

      #logo {
        width: 40vw;
        @media only screen and (min-width: $lg) {
          width: 13vw;
        }
      }
    }


    #links {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-end;
      gap: 20px;
      @media only screen and (max-width: $sm) {
        display: none;
      }

      a {
        color: var(--color-secondary);
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
