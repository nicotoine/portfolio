<script lang="ts">
	import APropos from './APropos.svelte';
	import PrimaryButton from './Commons/PrimaryButton.svelte';
	import ContactModal from './ContactModal/ContactModal.svelte';
	import MailIcon from './Icon/MailIcon.svelte';

	let displayContactModal: boolean = false;
</script>
<div class="mainDiv">
	<header>
		<main>
			<img src="me.jpg" alt="me" />
			<div>
				<h1>Nicolas Devos</h1>
				<h2>Développeur FullStack</h2>
			</div>
		</main>
		<footer>
			<PrimaryButton on:click={() => {displayContactModal = true}}>
				<MailIcon width="20px" style="fill: #ccc"></MailIcon>
				Me contacter
			</PrimaryButton>
		</footer>
	</header>

	<main>
		<APropos></APropos>
	</main>
</div>
<ContactModal bind:display={displayContactModal}></ContactModal>

<style lang="scss">
  @import '../../static/variables';
  @media only screen and (max-width: $xl) {
    div {
      header {
				background-color: var(--color-primary);
				padding-bottom: 50px;
        main {
          // add before blueRound.svg to the path
          display: flex;
          flex-direction: row;
          justify-content: space-around;
          align-items: center;
          padding: 20px;

          img {
            width: 40%;
            height: auto;
            border-radius: 50%;
          }

          div {
            display: flex;
            flex-direction: column;
            justify-content: center;
            gap: 5px;

            h1 {
              margin: 0;
              font-size: 1.5em;
              color: white;
            }

            h2 {
              margin: 0;
              font-size: 1em;
              color: var(--color-quaternary);
            }
          }
        }

        footer {
          display: flex;
          justify-content: center;
        }
      }

      main {
        padding: 20px;
      }
    }
  }
  @media only screen and (min-width: $xl) {
    div {
      display: flex;
      align-items: center;
			overflow: hidden;
      &.mainDiv {
        margin-top: 50px;

      }

      header {
        width: 33%;

				&::before {
          content: '';
          position: absolute;
          width: 33%;
          height: 800px;
          top: 0;
          transform: translateY(-35%);
          z-index: -1;
          background-color: var(--color-primary);
					border-radius: 0 50% 50% 0;
        }

        main {
          width: 100%;
          display: flex;
          justify-content: flex-start;
          padding: 20px;
          gap: 30px;

          img {
            width: 200px;
            height: auto;
            border-radius: 50%;
          }

          div {
            display: flex;
            flex-direction: column;
            justify-content: center;
            gap: 5px;

            h1 {
              margin: 0;
              font-size: 3em;
              color: white;
            }

            h2 {
              margin: 0;
              font-size: 1.5em;
              color: var(--color-quaternary);
            }
          }
        }

        footer {
          display: flex;
          justify-content: center;
        }
      }

      main {
        padding: 20px;
        width: 50%;

      }
    }
  }

</style>