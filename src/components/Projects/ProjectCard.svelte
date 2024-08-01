<script lang="ts">
	import PrimaryButton from '../Commons/PrimaryButton.svelte';

	export let image: string = '';
	export let name: string = '';
	export let techs: string[] = [];
	export let link: string = '';
	export let longDescription: boolean = false;

	let showBack: boolean = false;
</script>

<div class="cards">
	<div class="card card-front" class:showBack>
		<div class="img-container">
			<img class="card-img" src={image} alt='{name} image' style="{$$restProps.imgStyle}">
		</div>
		<div class="card-content">
			<div class="card-title">
				{#if link}
					<a href={link} target="_blank" rel="noopener noreferrer">{name}</a>
				{:else}
					{name}
				{/if}
			</div>
			<p class="card-text">
				<slot name="front"></slot>
			</p>

		</div>
		<div class="card-tags">
			{#each techs as tech}
				<span class="card-tag">{tech}</span>
			{/each}
		</div>
		{#if longDescription}
			<div class="btn-container">
				<PrimaryButton on:click={()=>{showBack = true}}>En savoir plus</PrimaryButton>
			</div>
		{/if}

	</div>

	<div class="card card-back" class:showBack>
		<div class="back-content">
			<h3>
				<span class="informationIcon">
					<i>
							<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
								<path
									d="M256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zM216 336l24 0 0-64-24 0c-13.3 0-24-10.7-24-24s10.7-24 24-24l48 0c13.3 0 24 10.7 24 24l0 88 8 0c13.3 0 24 10.7 24 24s-10.7 24-24 24l-80 0c-13.3 0-24-10.7-24-24s10.7-24 24-24zm40-208a32 32 0 1 1 0 64 32 32 0 1 1 0-64z" /></svg>
					</i>
						</span>
				Informations complémentaires
			</h3>
			<slot name="back"></slot>
		</div>
			<div class="btn-container">
				<PrimaryButton on:click={()=>{showBack = false}}>Retour</PrimaryButton>
			</div>
	</div>
</div>


<style lang="scss">
  .cards {
    position: relative;
  }

  .card {
    max-width: 24rem;
    border-radius: 0.375rem;
    overflow: hidden;
   	box-shadow: 0 2px 14px 1px rgba(0,0,0,0.1);
    transform-style: preserve-3d;

    height: 700px;
    width: 100%;
    position: relative;
    top: 0;

  }

  .card-front.showBack {
    transform: rotateY(-180deg);
  }

	.img-container{
		width: 100%;
		height: 24rem;
		overflow: hidden;
		display: flex;
		justify-content: center;
		align-items: center;
		border-bottom: 1px solid rgba(237, 242, 247, 0.6);
	}
  .card-img {
    width: 100%;
		object-position: center;
  }

  .card-content {
    padding: 1.5rem 1.5rem 0 1.5rem;
  }

  .card-title {
    font-weight: bold;
    font-size: 1.25rem;
    margin-bottom: 0.5rem;
    color: #1a202c;
  }

  .card-text {
    color: #4a5568;
    font-size: 1rem;
  }

  .card-tags {
    padding: 0.5rem 1.5rem 0.5rem;
		display: flex;
		flex-wrap: wrap;
  }

  .card-tag {
    display: inline-block;
    background-color: #edf2f7;
    border-radius: 9999px;
    padding: 0.25rem 0.75rem;
    font-size: 0.875rem;
    font-weight: 600;
    color: #4a5568;
    margin-right: 0.5rem;
    margin-bottom: 0.5rem;
  }

  .card-front {
    transform: rotateY(0deg);
    backface-visibility: hidden;
    transition: transform 0.5s;
  }

  .card-back {
    position: absolute;
    transform: rotateY(180deg);
    backface-visibility: hidden;
    transition: transform 0.5s;
		line-height: 1.5rem;

    &.showBack {
      transform: rotateY(0deg);
    }


		&::after {
			content: '';
			font-size: 1.2rem;
			position: absolute;
			width: 40%;
			height: 20%;
			top: 0;
			right: 0;
			border-radius: 0 0 0  100%;
      background: linear-gradient(90deg, var(--color-primary) 0%, var(--color-quaternary) 100%) right;
			z-index: 1;
		}
		&::before {
			content: '';
			font-size: 1.2rem;
			position: absolute;
			width: 40%;
			height: 20%;
			bottom: 0;
			left: 0;
			// gradient var(--color-quaternary)
			background: linear-gradient(90deg, var(--color-primary) 0%, var(--color-quaternary) 100%) left;
			border-radius:  0 100% 0 0;

    }

    .back-content {
      position: absolute;
      top: 0;
      left: 0;
      z-index: 2;
      color: black;
      display: flex;
      justify-content: flex-start;
      align-items: flex-start;
      flex-direction: column;
      gap: 10px;
      padding: 40px 20px 0 20px ;
      width: calc(100% - 40px);
      height: calc(100% - 40px);



      h3 {
        display: flex;
        align-items: center;
        gap: 10px;
        font-size: 1.5rem;
				margin-top: 2rem;
        margin-bottom: 2rem;
        color: var(--color-primary);

        .informationIcon {
          border-radius: 50%;
					background: white;
					padding: 0.2rem;
          i {
            display: flex;
            border-radius: 50%;
						padding: 0.2rem;
            svg {
              width: 1.5rem;
              height: 1.5rem;
              fill: var(--color-quaternary);
              stroke: var(--color-quaternary);
            }
          }
        }
      }

    }
  }

  a {
    color: var(--color-secondary);
    text-decoration: none;
  }

  .btn-container {
		position: absolute;
    display: flex;
    justify-content: center;
		align-items: center;
		width: 100%;
		bottom: 20px;
		z-index: 2;
  }

</style>