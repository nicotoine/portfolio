<script>
	import { base } from '$app/paths';
	import { Fa } from 'svelte-fa';
	import { faEnvelope, faPhone, faLocation} from '@fortawesome/free-solid-svg-icons';
</script>

<header>
	<img src="{base}/me.jpg" alt="me" />
	<div class="myInfos">
		<h1>Nicolas Devos</h1>
		<h2>Développeur FullStack</h2>
		<div class="contact">
			<small>
				<Fa icon={faEnvelope} size="1x" />
				nicolasdevos.45@gmail.com
			</small>
			<small>
				<Fa icon={faPhone} size="1x" />
				+33 7 81 32 28 09
			</small>
			<small>
				<Fa icon={faLocation} size="1x" />
				56 rue Saint Marceau, 45100 Orléans
			</small>
		</div>
	</div>
</header>

<style lang="scss">
  header {
    height: 150px;
    display: flex;
    background-color: var(--cv-primary-color);
    // change font style
    img {
      width: 150px;
      height: 150px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    }

    div.myInfos {
      display: flex;
      flex-direction: column;
      justify-content: center;
      margin-left: 20px;
      gap: 5px;

      h1 {
        font-size: 30px;
        margin: 0;
        color: white;
        font-weight: 500;
      }

      h2 {
        font-size: 18px;
        margin: 0;
        color: var(--cv-secondary-color);
        font-weight: 500;
      }

      .contact {
        margin-top: 10px;
				display: flex;
				flex-direction: row;
				flex-wrap: nowrap;
				gap: 10px;
        small {
					display: flex;
					flex-direction: row;
					gap: 5px;
					align-items: center;
          color: var(--cv-tertiary-color);
          text-decoration: none;
        }
      }
    }
  }
</style>