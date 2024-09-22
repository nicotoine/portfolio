<script lang="ts">
	import APropos from './APropos.svelte';
	import PrimaryButton from './Commons/PrimaryButton.svelte';
	import ContactModal from './ContactModal/ContactModal.svelte';
	import MailIcon from './Icon/MailIcon.svelte';
	import { base } from '$app/paths';


	let displayContactModal: boolean = false;

</script>
<div class="mainDiv">
	<main style="background-image: url({base}'/me_background.png')">
		<section class="pic">
			<span class="right-background" />
			<span class="left" />
			<div class="img-container">
				<span class="large-circle">
					<span class="white-circle">
						<span class="small-circle">
							<img src="{base}/me.png" alt="me" class="identity_pic" />
						</span>
					</span>
				</span>
				<div class="me">
					<h1>Nicolas Devos</h1>
					<h2>Développeur FullStack</h2>
				</div>
			</div>
		</section>
		<section class="description">
			<APropos></APropos>

				<PrimaryButton on:click={() => {displayContactModal = true}}>
					<MailIcon width="20px" style="fill: #ccc"></MailIcon>
					Me contacter
				</PrimaryButton>
		</section>
	</main>

</div>
<ContactModal bind:display={displayContactModal}></ContactModal>

<style lang="scss">
  @import '../../static/variables';

  main {
		min-height: 700px;
    background-repeat: no-repeat;
    background-position: left;
    margin: 0;
    background-size: 500px 700px;
    display: grid;
    grid-template-columns: 1fr 2fr;
    @media only screen and (max-width: $xl) {
			margin-top: 50px;
			display: flex;
			flex-direction: column;
      background-position: center 0;
      .left {
        position: absolute;
        top: 0;
        left: 0;
        width: calc(50% - 245px);
        height: 700px;
        background: var(--color-primary);
        z-index: -1;
      }
      .img-container {
        left: 50% !important;
        transform: translateX(-50%);
      }
			section.pic{
				width: 100%;
				min-height: 700px;
			}
			.description{
				justify-content: flex-start;
				margin-bottom: 50px;
			}
    }


    .img-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      margin-bottom: 20px;
      border-radius: 50%;
      position: absolute;
      top: 200px;
      left: 85px;

      .me {
        display: flex;
        flex-direction: column;
        align-items: center;
        // stroke text

        color: black;
        text-shadow: 3px 3px 0 white,
        -1px -1px 0 white,
        1px -1px 0 white,
        -1px 1px 0 white,
        1px 1px 0 white;

				text-wrap: nowrap;

        h1 {
          font-size: 3rem;
          margin: 0;
        }

        h2 {
          font-size: 2rem;
          margin: 0;
        }

      }

      img.identity_pic {
        width: 250px;
        height: 250px;
        object-fit: cover;
        filter: drop-shadow(0px 0px 10px rgba(0, 0, 0, 0.5));
        border-radius: 50%;
      }

    }

    span.large-circle {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 340px;
      height: 340px;
      border-radius: 50%;
      position: relative;
      background: linear-gradient(45deg, var(--color-primary) 0%, var(--color-quaternary) 100%) right;

      span.white-circle {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 265px;
        height: 265px;
        border-radius: 50%;
        background-color: white;
        position: relative;

        span.small-circle {
          display: flex;
          justify-content: center;
          align-items: center;
          width: 255px;
          height: 255px;
          border-radius: 50%;
          position: relative;
          background: linear-gradient(45deg, var(--color-primary) 0%, var(--color-quaternary) 100%) right;
        }
      }
    }
  }

  .description {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 20px;
    color: black;
    gap: 20px;
  }

</style>