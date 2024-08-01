<script lang="ts">
	import ProjectCard from './ProjectCard.svelte';

	let ijc: string[] = ['Java','Svelte','SpringBoot','Maven','Docker','Sass','TypeScript', 'GraphQL'];
</script>

<div class="content">
	<ProjectCard image="/projects/IJC.svg" name="Ingré Judo Club " techs={ijc}
							 link="https://ingre-judo-club.ffjudo.com/"
							 longDescription={true}
	>
		<div slot="front">
			<p>
					Etant membre du bureau du club de Judo d'Ingré, j'ai mis en place un intranet pour la gestion des membres du club.
			</p>
		</div>
		<div slot="back">
			<p>
				L'objectif de ce projet était de mettre en place un intranet pour la gestion des membres du club de Judo d'Ingré.
				J'ai également mis en place une partie publique pour les inscriptions aux cours. Cette partie publique est
				vouée à être améliorée pour permettre aux membres de reserver ou d'acheter des produits du club.
			</p>
			<b>Compétences mises en œuvre :</b>
			<ul>
				<li>
					Développement back-end (Java, SpringBoot, Maven)
				</li>
				<li>
					Développement front-end (Svelte, Sass, TypeScript)
				</li>
				<li>
					Base de données (MySQL)
				</li>
				<li>
					Mise en place d'APIs GraphQL
				</li>
			</ul>
		</div>
	</ProjectCard>


</div>

<style lang="scss">
  div.content {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 20px;
    flex-wrap: wrap;
  }


</style>
