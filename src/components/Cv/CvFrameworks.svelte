<script lang="ts">
	import ProgressBar from './ProgressBar.svelte';

	let frameworks = [
		{name: 'Angular', level: 70},
		{name: 'React', level: 80},
		{name: 'Svelte', level: 100},
		{name: 'Spring', level: 80}
	];

</script>

<section>
	<slot name="header"/>
	<ProgressBar informations={frameworks}></ProgressBar>
</section>
<style lang="scss">
  section {
    margin-top: 10px;
    display: grid;
    grid-gap: 20px;
    padding-bottom: 20px;
    border-bottom: 1px solid var(--cv-tertiary-color);
  }
</style>