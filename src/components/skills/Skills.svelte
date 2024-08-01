<script lang="ts">
	import Carousel from '../Carousel/Carousel.svelte';
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';
	import { tooltip } from "@svelte-plugins/tooltips";

	let skills: { iconPath: string, name: string}[] = [];

	skills.push({
		iconPath: 'skill/svelte.png',
		name: 'Svelte'
	});
	skills.push({
		iconPath: 'skill/reactnative.png',
		name: 'ReactNative'
	});
	skills.push({
		iconPath: 'skill/TypeScript.png',
		name: 'TypeScript'
	});
	// Java
	skills.push({
		iconPath: 'skill/java.svg',
		name: 'Java'
	});
	// Spring
	skills.push({
		iconPath: 'skill/Spring.svg',
		name: 'Spring'
	});
	// Docker
	skills.push({
		iconPath: 'skill/docker.png',
		name: 'Docker'
	});
	// angular
	skills.push({
		iconPath: 'skill/angular.png',
		name: 'Angular'
	});
	// git
	skills.push({
		iconPath: 'skill/git.png',
		name: 'Git'
	});
	// bitbucket
	skills.push({
		iconPath: 'skill/bitbucket.png',
		name: 'Bitbucket'
	});
	// mysql
	skills.push({
		iconPath: 'skill/mysql.svg',
		name: 'MySQL'
	});
	// elastic search
	skills.push({
		iconPath: 'skill/elasticsearch.png',
		name: 'ElasticSearch'
	});

	// php
	skills.push({
		iconPath: 'skill/php.svg',
		name: 'PHP'
	});


	let perPage: number = 3;

	onMount(() => {
		// check if the browser is available
		if (!browser) return;

		function checkSize() {
			if (window.innerWidth < 600) {
				perPage = 2;
			} else {
				perPage = 3;
			}
		}

		checkSize();
		window.addEventListener('resize', () => {
			checkSize();
		});
	});
</script>

<main>
	<h2>Mes compétences</h2>
	<div>
		{#if perPage === 2}
			<Carousel autoplay={2000} {perPage}>
				{#each skills as skill, index (index)}
					<div class="skill" title="{skill.name}" use:tooltip={{position:"left"}}>
						<img src={skill.iconPath} alt={skill.name}/>
					</div>
				{/each}
			</Carousel>
		{:else}
			<Carousel autoplay={2000} {perPage}>
				{#each skills as skill, index (index)}
					<div  class="skill" title="{skill.name}" use:tooltip={{position:"left"}}>
						<img src={skill.iconPath} alt={skill.name} />
					</div>
				{/each}
			</Carousel>
		{/if}


	</div>

</main>
<style lang="scss">
	@import '../../../static/variables';
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    background: #eee;
    color: var(--color-secondary);
    flex-direction: column;
    padding-bottom: 60px;
		padding-top: 20px;
		h2 {
			font-size: 1.7rem;
			margin-bottom: 20px;
			color: var(--color-primary);
		}
    & > div {
		@media only screen and (min-width: $md) {
			height: 200px;
		}
      width: 80%;
			display: flex;
			justify-content: center;
			align-items: center;
    }
  }
	div.skill {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100px;
		width: 50px;
		img {
			max-height: 100px;
			max-width: 100px;
		}
	}
	@media only screen and (min-width: $md) {
		div.skill {
			display: flex;
			justify-content: center;
			align-items: center;
			height: 150px;
			width: 100px;
			img {
				max-height: 150px;
				max-width: 300px;
			}
		}
	}
</style>