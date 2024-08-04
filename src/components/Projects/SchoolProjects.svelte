<script lang="ts">
	import ProjectCard from './ProjectCard.svelte';

	let gpeTechs: string[] = ['PHP', 'MySQL', 'ReactNative', 'Python', 'FastAPI', 'Mercure', 'RabbitMQ', 'DockerSwarm', 'Ansible'];
	let tmdbTechs: string[] = ['ReactJS', 'Angular', 'Php', 'Symfony', 'MySQL'];
	let quantumMotors: string[] = ['Ansible', 'DockerSwarm', 'fluentd', 'Kibana', 'Prometheus', 'BlackBoxExporter', 'Grafana'];
</script>

<div class="content">

	<ProjectCard image="/projects/cosport.jpg" name="CoSport" techs={gpeTechs}
							 link="https://play.google.com/store/apps/details?id=com.gpe.cosport"
							 longDescription={true}
	>
		<div slot="front">
			<p>
				Création d'une application mobile de mise en relation d'amateurs de sport. Application disponible sur le Play
				Store.
			</p>
		</div>
		<div slot="back">
			<p>
				L'objectif de ce projet était de créer une application mobile permettant de mettre en relation des amateurs de
				sport.
			</p>
			<b>Compétences mises en œuvre :</b>
			<ul>
				<li>
					Développement mobile (ReactNative)
				</li>
				<li>
					Développement back-end (PHP,Symfony)
				</li>
				<li>
					Base de données (MySQL)
				</li>
				<li>
					Développement de micro-services (Python, FastAPI)
				</li>
				<li>
					Utilisation de protocol SSE (Mercure)
				</li>
				<li>
					Utilisation d'outils tels que RabbitMQ, DockerSwarm, Ansible
				</li>
				<li>
					Mise en place d'une CI/CD
				</li>
			</ul>
		</div>
	</ProjectCard>
	<ProjectCard image="/projects/TMDB.png" name="The movie DB" techs={tmdbTechs}
							 link="https://www.themoviedb.org/?language=fr"
							 longDescription={true}
	>
		<div slot="front">
			<p>
				Reproduction de l'application The Movie DB en ReactJS et Angular
			</p>

		</div>
		<div slot="back">
			<p>
				L'objectif de ce projet était de reproduire l'application The Movie DB en ReactJS et en Angular afin de comparer
				les deux technologies.
			</p>
			<b>Protocole d’expérimentation :</b>
			<ul>
				<li>Création & exploitation des données d’un formulaire</li>
				<li>Interrogation d’une API</li>
				<li>Gestion d’événements IHM</li>
				<li>Gestion des cycles de vie</li>
				<li>Utilisation des mêmes librairies</li>
				<li>Utilisation de librairies communautaires</li>
				<li>Utilisation d’un token d’authentification (Token Interceptor)</li>
			</ul>

		</div>
	</ProjectCard>
	<ProjectCard image="/projects/quantum.png" name="Quantum Motor" techs={quantumMotors}
							 longDescription={true}
	>
		<div slot="front">
			<p>
				Projet "Cloud" visant à mettre en place une infrastructure applicative pour l'application Quantum Motor.
			</p>

		</div>
		<div slot="back">
			<p>

				L'objectif de ce projet était de déployer une infrastructure applicative pour l'application Quantum Motor sur plusieurs serveurs simultanément.
			</p>
			<b>Compétences mises en œuvre :</b>
			<ul>
				<li>
					Automatisation de déploiement (Ansible)
				</li>
				<li>
					Orchestration de conteneurs (DockerSwarm)
				</li>
				<li>
					Collecte de logs (fluentd)
				</li>
				<li>
					Analyse de logs (Kibana)
				</li>
				<li>
					Supervision (Prometheus, BlackBoxExporter, Grafana)
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
