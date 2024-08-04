<script lang="ts">

</script>

<slot name="header" />
<div class="experience">
	<div class="school">
		<header>
			<h4>
				Master Architecte Logiciel, développeur d'applications
			</h4>
			<p>
				de Sept. 2022 à ce jour
			</p>
		</header>
		<main>
			<p>
				&Eacute;cole alternance informatique Paris, ETNA Ivry-sur-Seine
			</p>
			<ul>
				<li>Programmation Web Avancée</li>
				<li>Architecture des applications</li>
				<li>Conception et développement d'applications</li>
				<li>Programmation mobile avancée</li>
				<li>Algorithmique avancée</li>
			</ul>

		</main>
	</div>
	<div class="school">
		<header>
			<h4>
				Licence Professionnelle Développement Web et Mobile
			</h4>
			<p>
				de Sept. 2021 à Août 2022
			</p>
		</header>
		<main>
			<p>
				IUT Orléans
			</p>
			<ul>
				<li>Programmation Web</li>
				<li>Programmation Mobile</li>
			</ul>
		</main>
	</div>
	<div class="school">
		<header>
			<h4>
				DUT Informatique
			</h4>
			<p>
				de Sept. 2019 à Août 2021
			</p>
		</header>
		<main>
			<p>
				Université du Havre
			</p>
			<ul>
				<li>Programmation orientée objet</li>
				<li>Programmation Web</li>
				<li>Base de données</li>
			</ul>

		</main>
	</div>

</div>

<style lang="scss">
  .experience {
    display: grid;
    grid-gap: 4px;
    padding-bottom: 20px;
    margin-right: 20px;

    header {
      display: grid;
      grid-template-columns: 2fr 1fr;
      gap: 5px;
      justify-content: space-between;
      margin: 0;

      h4 {
        color: var(--cv-primary-color);
        font-size: 15px;
        margin: 0;
        font-weight: 600;
      }
    }

    p {
      margin: 0;
    }

    .school {
      display: grid;
      grid-gap: 10px;
      margin-bottom: 10px;

      main {
        display: grid;
        padding-left: 20px;
        grid-gap: 5px;

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