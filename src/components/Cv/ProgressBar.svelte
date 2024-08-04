<script lang="ts">
	export let informations: { name: string, level: number }[] = [];

	informations.sort((a, b) => b.level - a.level);
</script>

<main>
	{#each informations as information}
		<div class="language">
			<h4>{information.name}</h4>
			<div class="border">
				<div class="grey" style="width:{information.level}%"></div>
			</div>
		</div>
	{/each}
</main>

<style lang="scss">
	main{
		display: grid;
		gap: 10px;
		.language {
			display: grid;
			grid-template-columns: 1fr;
			gap: 10px;

			h4 {
				margin: 0;
			}

			.border {
				overflow: hidden;
				background-color: var(--cv-secondary-color);
			}

			.grey {
				background-color: var(--cv-primary-color);
				height: 5px;
			}
		}
	}
</style>