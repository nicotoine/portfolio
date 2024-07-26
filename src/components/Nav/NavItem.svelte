<script lang="ts">
	export let path: string;
	export let name: string;

</script>

<li>
	<a href = {path}>{name}</a>
</li>

<style lang="scss">
	li{
		display: inline;
		margin: 0 10px;
		a{
			text-decoration: none;
			color: var(--color-tertiary);
		}
	}
</style>