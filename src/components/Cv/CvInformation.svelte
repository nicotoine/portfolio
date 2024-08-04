<script lang="ts">

</script>

<slot name="header" />
<main>
	<div>
		<h4>
			Dates de naissance
		</h4>
		17 Juillet 1999
	</div>
	<div>
		<h4>
			Permis de conduire
		</h4>
		Permis B
	</div>
	<div>
		<h4>
			LinkedIn
		</h4>
		https://www.linkedin.com/in/nicolas-devos-897505192/
	</div>
	<div>
		<h4>
			Site web
		</h4>
		https://nicotoine.github.io/portfolio/
	</div>

</main>

<style lang="scss">
  main {
    display: grid;
    grid-gap: 10px;
    padding: 15px 0;
		border-bottom: 1px solid var(--cv-tertiary-color);
    h4 {
      color: var(--cv-primary-color);
      font-size: 15px;
      margin: 0;
      font-weight: 600;
    }
  }
</style>