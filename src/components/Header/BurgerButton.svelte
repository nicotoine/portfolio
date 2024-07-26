<button on:click>
	<svg
		xmlns="http://www.w3.org/2000/svg"
		viewBox="0 0 24 24"
		fill="none"
		stroke={$$restProps.stroke}
		stroke-width="2"
		stroke-linecap="round"
		stroke-linejoin="round"
		class="feather feather-menu" style="width: 5vw; height: 5vw;">
		<line x1="3" y1="12" x2="21" y2="12"></line>
		<line x1="3" y1="6" x2="21" y2="6"></line>
		<line x1="3" y1="18" x2="21" y2="18"></line>
	</svg>
</button>

<style lang="scss">
	button {
		width: 30px;
		height: 30px;
		border-radius: 8px;
		background-color: transparent;
		border: 1px solid #ccc;
		cursor: pointer;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>