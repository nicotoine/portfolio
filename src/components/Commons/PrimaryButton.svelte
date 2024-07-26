<script lang="ts">
</script>

<button on:click|preventDefault|stopPropagation>
	<slot></slot>
</button>

<style lang="scss">
	button{
		background: var(--color-primary);
		color: white;
		border: none;
		padding: 10px 20px;
		border-radius: 5px;
		cursor: pointer;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 5px;
		font-size: 1.2em;
	}
</style>