<script lang="ts">

	import { onMount } from 'svelte';
	import { browser } from '$app/environment';
	import Presentation from '../components/Presentation.svelte';
	import Skills from '../components/skills/Skills.svelte';
	import Projetcs from '../components/Projects/Projetcs.svelte';
	import Schools from '../components/Schools/Schools.svelte';
	import Header from '../components/Header/Header.svelte';
	import Footer from '../components/Footer/Footer.svelte';

	onMount(() => {
		if (!browser) return;
		document.title = 'Nicolas Devos - Développeur FullStack';
	});
</script>
<Header />
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

<Footer></Footer>


<style>
    #presentation {
        position: relative;
        z-index: 1;
        overflow: visible;
        top: -50px;
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