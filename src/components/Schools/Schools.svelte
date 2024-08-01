<script lang="ts">

import SchoolCard from './SchoolCard.svelte';
</script>

<main>
	<h2>
		Mon parcours scolaire
	</h2>

	<div>
		<SchoolCard
			image="/schools/Lycee.svg"
			school="Lycée Maurice Genevoix"
			description="Spécialisation en Sciences et Technologies de l'Industrie et du Développement Durable, option Systèmes d'Information et Numérique"
			date="2019"
			diploma="Bac STI2D"
		/>
		<SchoolCard
			image="/schools/iut.jpg"
			school="IUT du Havre"
			description="Deux ans d'études en informatique, spécialisation en développement orienté objet"
			date="2021"
			diploma="DUT Informatique"
		/>
		<SchoolCard
			image="/schools/iuto.jpg"
			school="IUT d'Orléans"
			description="Un an de Licence Informatique web et mobile en alternance chez Arondor"
			date="2023"
			diploma="Licence Informatique"
		/>
		<SchoolCard
			image="/schools/ETNA.png"
			school="ETNA"
			description="Deux ans de formation avec une spécialisation en développement web et mobile en alternance chez Arondor"
			date="2024"
			diploma="Master Informatique"
		/>
	</div>

</main>

<style lang="scss">
	@import '../../../static/variables';
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 20px;
		height: 500px;
    h3 {
      font-size: 1.7rem;
      margin-bottom: 10px;
			color: var(--color-primary);
    }
		div {
			display: flex;
			align-items: center;
			justify-content: center;
			gap: 20px;
			flex-direction: row;
			flex-wrap: wrap;
		}
  }

</style>