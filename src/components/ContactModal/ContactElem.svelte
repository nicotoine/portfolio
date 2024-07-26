<script lang="ts">
	export let name: string;
	export let activeName: string;

	const onclick = () => {
		activeName = name;
	}

	$: active = activeName === name;
</script>

<button on:click={onclick} class:active {...$$restProps}>
	<slot></slot>
</button>

<style lang="scss">
	button {
		background: none;
		cursor: pointer;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 5px;
		padding: 5px;
		border-radius: 50%;
		border: 1px solid #ccc;
	}

	.active {
		background: var(--color-primary);
		color: white;
	}
</style>

