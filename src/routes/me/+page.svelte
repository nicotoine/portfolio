<script lang="ts">
	import Presentation from '../../components/Presentation.svelte';
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';
	import Skills from '../../components/skills/Skills.svelte';
	import Schools from '../../components/Schools/Schools.svelte';
	import Projetcs from '../../components/Projects/Projetcs.svelte';

	onMount(() => {
		if (!browser) return;
		document.title = 'Nicolas Devos - Développeur FullStack';
	});
</script>

<section id="presentation">
	<Presentation></Presentation>
</section>
<section id="skills">
	<Skills></Skills>
</section>
<section id="projects">
	<Projetcs></Projetcs>
</section>
<section id="schools">
	<Schools></Schools>
</section>

<style>
    #presentation {
        background-color: var(--color-primary);
        position: relative;
        z-index: 1;
        overflow: visible;
				top: -100px;
				margin-bottom: -100px;
    }

    #skills {
        position: relative;
        z-index: 2;
    }

    #projects {
        margin-top: 20px;
    }

    #schools {
        margin-top: 20px;
    }
</style>