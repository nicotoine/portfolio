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
	import { base } from '$app/paths';
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';
	import { Fa } from 'svelte-fa';
	import { faDownload } from '@fortawesome/free-solid-svg-icons';
	import '@fontsource/poppins'; // Defaults to weight 400

</script>

<section>
	<Page size={PageSizes.A4}>
		<a href="{base}/cv/cv.pdf" download="cv.pdf">
			<Fa icon={faDownload} />
			Télécharger le CV
		</a>
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
</section>

<style lang="scss">
  :root {
    --cv-primary-color: #303843;
    --cv-secondary-color: #ddd;
    --cv-tertiary-color: #bbb;
    --cv-quaternary-color: #666;
  }

  * {
    color: var(--cv-quaternary-color);
    font-size: 12px;
    font-family: 'Poppins', sans-serif;
    line-height: 1.3;
  }

	section {
		zoom: 1;
		@media (max-width: 768px) {
			zoom: 0.4;
		}
	}


  a {
    color: var(--cv-primary-color);
    text-decoration: none;
    display: block;
    padding: 10px;
    background-color: var(--cv-secondary-color);
    margin: 10px 0;
    position: absolute;
    top: 0;
    right: 5px;
  }

  main {
    display: grid;
    grid-template-columns: 3fr 1fr;
    grid-gap: 20px;
    padding: 30px;

    h3 {
      color: var(--cv-primary-color);
      font-size: 18px;
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