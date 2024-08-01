<script lang="ts">
	import { fly } from 'svelte/transition';
	import SchoolProjects from './SchoolProjects.svelte';
	import EnterpriseProject from './EnterpriseProject.svelte';
	import PersonnalProjects from './PersonnalProjects.svelte';

	let projectsTypes: string[] = ['Scolaires', 'Professionnels', 'Personnels'];
	let index: number = 0;
	let lastIndex: number = 0;
	let x: string = "100%";


	const handleChangeType = (i: number) => {
		lastIndex = index;
		index = i;
		x = index > lastIndex ? "100%" : "-100%" ;
		const projects = document.getElementById('projects');
		projects?.scrollIntoView({behavior: "smooth"});
	};
</script>

<main id="projects">
	<h2 >
		Projets réalisés
	</h2>
	<header>
		<ul>
			{#each projectsTypes as type, i}
				<li class:active={index === i}>
					<button on:click={() => handleChangeType(i)}>Projets {type}</button>
				</li>
			{/each}
		</ul>
	</header>
	{#if projectsTypes[index] === 'Scolaires'}
		<main in:fly={{ x: x}}>
			<SchoolProjects></SchoolProjects>
			</main>
	{/if}
	{#if projectsTypes[index] === 'Professionnels'}
		<main in:fly={{ x: x }}>
			<EnterpriseProject></EnterpriseProject>
		</main>
	{/if}
	{#if projectsTypes[index] === 'Personnels'}
		<main in:fly={{ x: x}}>
			<PersonnalProjects></PersonnalProjects>
		</main>
	{/if}

</main>

<style lang="scss">
  @import '../../../static/variables';

  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;

    h2 {
      font-size: 1.7rem;
      margin-bottom: 10px;
			color: var(--color-primary);
    }

    header {

      ul {
        display: flex;
        justify-content: center;
        align-items: center;
        border-bottom: 1px solid #ccc;
				padding: 0;
				gap: 10px;


        li {
          list-style: none;

          button {
            background: transparent;
            border: none;
            cursor: pointer;
            font-size: 1rem;
            padding: 10px;
            transition: background-color 0.5s;

            &:hover {
              color: var(--color-quaternary);
            }
          }

          span.border {
            width: 100%;
            height: 2px;
            background: transparent;
            display: block;
          }

          &::after {
            display: block;
            content: '';
            border-bottom: solid 3px var(--color-quaternary);
            transform: scaleX(0);
            transition: transform 250ms ease-in-out;
          }

          &:hover::after {
            transform: scaleX(1);
          }

          &.active {
            &::after {
              transform: scaleX(1);
            }

            button {
              color: var(--color-quaternary);
            }
          }

        }
      }
    }
  }

</style>