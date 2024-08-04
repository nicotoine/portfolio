<script lang="ts">
	import Page from '../../components/Page.svelte';
	import { PageSizes } from '../../models/PageSizes';
	import CvHeader from './CvHeader.svelte';
	import CvWorkExperience from './CvWorkExperience.svelte';
	import CVSchool from './CVSchool.svelte';
	import CvInformation from './CvInformation.svelte';
	import CvLangages from './CvLangages.svelte';
	import CvFrameworks from './CvFrameworks.svelte';
	import CvDatabase from './CvDatabase.svelte';
</script>

<Page size={PageSizes.A4}>
	<CvHeader></CvHeader>
	<main>
		<div>
			<CvWorkExperience>
				<h3 slot="header">Expérience professionnelle</h3>
			</CvWorkExperience>
			<CVSchool>
				<h3 slot="header">Formation</h3>
			</CVSchool>
		</div>
		<aside>
			<CvInformation>
				<h3 slot="header">Informations</h3>
			</CvInformation>
			<CvLangages>
				<h3 slot="header">Languages</h3>
			</CvLangages>
			<CvFrameworks>
				<h3 slot="header">Frameworks</h3>
			</CvFrameworks>
			<CvDatabase>
				<h3 slot="header">Base de données</h3>
			</CvDatabase>
		</aside>
	</main>
</Page>

<style lang="scss">
  :root {
    --cv-primary-color: #303843;
    --cv-secondary-color: #ddd;
    --cv-tertiary-color: #bbb;
		--cv-quaternary-color: #666;
  }
	* {

		font-family: 'Times New Roman', Times, serif;
    color: var(--cv-quaternary-color);
    font-size: 14px;

	}
	main {
		display: grid;
		grid-template-columns: 2fr 1fr;
		grid-gap: 20px;
		padding: 30px;
		h3 {
			color: var(--cv-primary-color);
			font-size: 20px;
			margin: 0;
			font-weight: 400;
		}
		div {
			display: grid;
			grid-gap: 20px;
			border-right: 1px solid var(--cv-tertiary-color);
		}
	}

</style>