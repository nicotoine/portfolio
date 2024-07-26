<script lang="ts">
	import { onMount } from 'svelte'

	let overlay: HTMLDivElement

	/**
	 * Check if container exists, if not create it and append it to the body
	 */
	onMount(() => {
		let container: HTMLElement | null = document.getElementById('overlay-container')
		if (!container) {
			container = document.body.appendChild(document.createElement('div'))
			container.id = 'overlay-container'
		}
		container.appendChild(overlay)

		return () => container?.removeChild(overlay)
	})
</script>

<div bind:this={overlay} class="overlay {$$props.class}" style="{$$props.style}">
	<slot />
</div>


<style lang="scss">
	.overlay {
		position: relative;
		z-index: 1000;
	}
</style>