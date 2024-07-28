<script lang="ts">
	export let school: string = 'Epitech';
	export let image: string = 'epitech.png';
	export let description: string = 'Epitech est une école d\'informatique qui forme en 5 ans des experts en informatique.';
	export let date: string = '2018-2023';
	export let diploma: string = 'Expert en informatique';

	export let display: boolean = false;

</script>
<div class="cards">
	<div class="card card-front" style="background-image: url({image})" />
	<div class="card card-back" style="background-image: url({image})">
		<div class="card-content">
			<div class="title">
			<h3>{school}</h3>
			<p>({date})</p>

			</div>
			<p>{description}</p>
			<p class="diploma">{diploma}</p>
		</div>
	</div>

</div>


<style lang="scss">
  .cards {
		position: relative;
    .card {
      display: flex;
      cursor: pointer;
      position: relative;
      width: 300px;
      height: 300px;
      border-radius: 50%;
      overflow: hidden;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background-position: center;
      background-repeat: no-repeat;
      background-size: 60%;
      transform-style: preserve-3d;
      transition: transform 0.5s;


      .card-content {
				width: calc(100% - 60px);
				height: calc(100% - 120px);
        background: rgba(21, 39, 75, 0.9);
        color: white;
        padding: 30px ;
        border-radius: 10px;
        text-align: center;
				display: flex;
				flex-direction: column;
				justify-content: center;
				.title {
					margin-bottom: 15px;
        }
        h3 {
          font-size: 1.5rem;
					margin-bottom: 0;
        }

        p {
          margin: 0;
					&.diploma {
						margin-top: 10px;
						font-weight: bold;
						text-decoration: underline;

          }
        }
      }
    }

    .card-front {
      display: flex;
      transform: rotateY(0deg);
      border-radius: 50%;
      overflow: hidden;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background-position: center;
      background-repeat: no-repeat;
      background-size: 60%;
      transition: transform 0.5s;
      backface-visibility: hidden;

    }

    .card-back {
      position: absolute;
			top: 0;
      transform-style: preserve-3d;
      transform: rotateY(180deg);
      backface-visibility: hidden;
      transition: transform 0.5s;
    }

    &:hover {
      .card-front {
        transform: rotateY(180deg);
      }

      .card-back {
        transform: rotateY(0deg);
      }
    }

  }


</style>
