<script lang="ts">

</script>

<slot name="header" />
<div id="arondor" class="experience">
	<header>
		<h4>Développeur FullStack</h4>
		de Août 2021 à ce jour
	</header>
	<p>
		Arondor, Orléans
	</p>
	<section>

		<div class="mission">
			<h5>
				Responsable technique - Association pour la Recherche en Immunologie et en Transplantation ( ARIT )
			</h5>
			<ul>
				<li>Maintenance et évolution d'une application PHP dédiée à l'ARIT.</li>
				<li>Responsable de la migration de l'application vers une nouvelle version de PHP.</li>
				<li>Assurance d'un support technique pour les utilisateurs.</li>
			</ul>
		</div>
		<div class="mission">
			<h5>
				Responsable d'un support technique niveau 1 et intervention sur les niveaux 2 et 3. ( FAST2 )
			</h5>
			<ul>
				<li>Fourniture d'un support technique aux utilisateurs.</li>
				<li>Gestion de la charge de travail des techniciens du support de niveau 1.</li>
				<li>Intervention sur les niveaux 2 et 3 en cas de besoin. ( Appels clients, réalisation de corrections de bugs,
					etc. )
				</li>
			</ul>
		</div>
		<div class="mission">
			<h5>
				Responsable technique Front - Migration technologique d'une application web ( FAST2 )
			</h5>
			<ul>
				<li>
					Migration de la technologie Google Web Toolkit vers Svelte.
				</li>
				<li>
					Formation et accompagnement des développeurs sur la technologie Svelte.
				</li>
				<li>
					Conception et développement d'APIs REST en Spring Boot.
				</li>
			</ul>
		</div>
	</section>
</div>

<style lang="scss">
  .experience {
    display: grid;
    grid-gap: 4px;
    border-bottom: 1px solid var(--cv-tertiary-color);
    padding-bottom: 20px;
    margin-right: 20px;

    header {
      display: flex;
      flex-direction: row;
      gap: 5px;
      justify-content: space-between;
      margin: 0;

      h4 {
        color: var(--cv-primary-color);
        font-size: 17px;
        margin: 0;
        font-weight: 600;
      }
    }

    p {
      margin: 0;
    }

    section {
      padding-left: 20px;

      .mission {
        display: grid;
        grid-gap: 10px;
        margin-top: 10px;

        h5 {
          color: var(--cv-primary-color);
          font-size: 15px;
          margin: 0;
          font-weight: 600;
        }

        ul {
          margin: 0;
          padding-left: 20px;

          li {
            margin: 0;
          }
        }
      }
    }
  }
</style>