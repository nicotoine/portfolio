
<script lang="ts">
	import Siema from 'siema'
	import { onMount, createEventDispatcher } from 'svelte'
	import { browser } from '$app/environment';

	export let perPage = 3
	export let loop = true
	export let autoplay = 0
	export let duration = 500
	export let easing = 'ease-out'
	export let startIndex = 0
	export let draggable = true
	export let multipleDrag = true
	export let threshold = 20
	export let rtl = false
	let currentIndex = startIndex;

	let siema: HTMLElement
	let controller :Siema
	let timer: number;
	const dispatch = createEventDispatcher()

	$: pips = controller ? controller.innerElements : []
	$: currentPerPage = controller ? controller.perPage : perPage

	onMount(() => {
		if(!siema || !browser) return
		controller = new Siema({
			selector: siema,
			perPage: typeof perPage === 'object' ? perPage : Number(perPage),
			loop,
			duration,
			easing,
			startIndex,
			draggable,
			multipleDrag,
			threshold,
			rtl,
			onChange: handleChange
		})

		if(autoplay) {
			timer = setInterval(right, autoplay);
		}
		return () => {
			autoplay && clearInterval(timer)
			controller.destroy()
		}
	})

	export function isDotActive(currentIndex: number, dotIndex: number): boolean  {
		if (currentIndex < 0) currentIndex = pips.length + currentIndex;
		return currentIndex >= dotIndex*currentPerPage && currentIndex < (dotIndex*currentPerPage)+currentPerPage
	}

	export function left () {
		controller.prev()
	}

	export function right () {
		controller.next()
	}

	export function  go(index: number): void {
		controller.goTo(index)
	}

	export function pause() {
		clearInterval(timer);
	}

	export function resume() {
		if (autoplay) {
			timer = setInterval(right, autoplay);
		}
	}

	function handleChange () {
		currentIndex = controller.currentSlide
		dispatch('change', {
			currentSlide: controller.currentSlide,
			slideCount: controller.innerElements.length
		} )
	}


</script>
<div class="carousel">
	<div class="slides" bind:this={siema}>
		<slot></slot>
	</div>
</div>

<style>
    .carousel {
        position: relative;
        width: 100%;
        justify-content: center;
        align-items: center;
    }
</style>
