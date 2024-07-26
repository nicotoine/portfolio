<script lang="ts">
	import NavItem from './NavItem.svelte';

	export let display: boolean = false;
	import { slide } from 'svelte/transition';
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';

	// on window resize, hide the menu
	onMount(
		() => {
			if (!browser) return;
			window.addEventListener('resize', () => {
				display = false;
			});
		}
	);
</script>

{#if display}
	<ul transition:slide>
		<NavItem path="/" name="Home"></NavItem>
		<NavItem path="/about" name="About"></NavItem>
	</ul>
{/if}

<style>
    ul {
        z-index: 1;
        flex-direction: column;
        align-items: flex-start;
        gap: 15px;
        padding: 20px;
        margin: 0;
        display: flex;
    }
</style>