<script lang="ts">
	import ProgressBar from './ProgressBar.svelte';

	let databases = [
		{name: 'MySQL/MariaDB', level: 90},
		{name: 'ElasticSearch', level: 80}
	];

</script>

<section>
	<slot name="header"/>
	<ProgressBar informations={databases}></ProgressBar>
</section>
<style lang="scss">
  section {
    margin-top: 10px;
    display: grid;
    grid-gap: 20px;
    padding-bottom: 20px;
  }
</style>