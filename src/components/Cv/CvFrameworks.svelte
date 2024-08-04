<script lang="ts">

	import ProgressBar from './ProgressBar.svelte';
	// langage : java, typescript, python, php, html/css
	let langages = [
		{name: 'Java', level: 100},
		{name: 'TypeScript', level: 100},
		{name: 'Python', level: 80},
		{name: 'PHP', level: 70},
		{name: 'HTML/CSS', level: 100}
	];

</script>

<section>
	<slot name="header"/>
	<ProgressBar informations={langages}></ProgressBar>
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