<script lang="ts">
	import ProjectCard from './ProjectCard.svelte';

	let arit: string[] = ['PHP', 'MySQL', 'Linux', 'Apache', 'JavaScript', 'Ajax', 'Docker'];
	let fast2: string[] = ['Java','Svelte','SpringBoot','Maven','Docker','Sass','TypeScript','OpenSearch'];
</script>

<div class="content">
	<ProjectCard image="/projects/arit.png" name="ARIT " techs={arit}
							 link="https://www.chu-bordeaux.fr/Les-services/Service-d-Urologie,-andrologie-et-transplantation-r%C3%A9nale/LA-TRANSPLANTATION-RENALE/"
							 longDescription={true}
							 imgStyle="width: 80%;"
	>
		<div slot="front">
			<p>

				Responsable technique de l'application de gestion des patients transplantés rénaux pour l'Association de
				Recherche Immunologie et Transplantation.
			</p>
		</div>
		<div slot="back">
			<p>
				Mon rôle était de gérer l'application de gestion des patients transplantés rénaux pour l'ARIT.

				Je devais assurer la maintenance de l'application, la mise en place de nouvelles fonctionnalités et la
				correction de bugs.
			</p>
			<b>Compétences mises en œuvre :</b>
			<ul>
				<li>
					Développement back-end (PHP,Composer)
				</li>
				<li>
					Développement front-end (JavaScript, Ajax, Smarty)
				</li>
				<li>
					Base de données (MySQL)
				</li>
				<li>
					Relation client ( spécifications, recette, formation, support)
				</li>
				<li>
					Utilisation d'outils tels que Docker
				</li>
			</ul>
		</div>
	</ProjectCard>
	<ProjectCard image="/projects/FAST2.svg" name="Fast2" techs={fast2}
							 link="https://www.uxopian.com/fr/fast2"
							 longDescription={true}
							 imgStyle="width: 80%;"
	>
		<div slot="front">
			<p>
				Migration technologique de l'application Fast2 pour l'entreprise Uxopian.
			</p>

		</div>
		<div slot="back">
			<p>
				L'objectif de ce projet était de migrer l'application Fast2 de GWT vers Svelte. J'étais responsable de la
				partie front-end de l'application.
			</p>
			<b>Compétences mises en œuvre :</b>
			<ul>
				<li>Mise en place d'une architecture front-end en Svelte (Architecture 'Atomic Design')</li>
				<li>Formation des équipes à l'utilisation de Svelte</li>
				<li>Revues de code (Code Review)</li>
				<li>Mise en place d'API REST en SpringBoot</li>
				<li>Création d'un moteur de workflow en Svelte</li>
				<li>Utilisation d'une base de données OpenSearch (ElasticSearch)</li>
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
