<script lang="ts">
import Header from '../components/Header/Header.svelte';
</script>

<Header />
<main>
	<slot></slot>
</main>

<style lang="scss">
		main {
			position: relative;
			z-index: 1;
    }

    :global(:root){
        --color-primary:#3b5997;
        --color-secondary: #333;
        --color-tertiary: #777;
        --color-quaternary: #008DD5;
        --color-quinary: #333;
        --color-senary: #333;
        --color-septenary: #333;
        --color-octonary: #333;
        --color-nonary: #333;
        --color-denary: #333;
        --color-elevenary: #333;
        --color-twelveary: #333;
        --color-thirteenary: #333;
        --color-fourteenary: #333;
        --color-fifteenary: #333;
        --color-sixteenary: #333;
        --color-seventeenary: #333;
        --color-eighteenary: #333;
        --color-nineteenary: #333;
        --color-twentyary: #333;
        --color-twentyoneary: #333;
        --color-twentytwoary: #333;
        --color-twentythreeary: #333;
        --color-twentyfourary: #333;
        --color-twentyfiveary: #333;
        --color-twentysixary: #333;
        --color-twentysevenary: #333;
        --color-twentyeightary: #333;
        --color-twentynineary: #333;
        --color-thirtyary: #333;
        --color-thirtyoneary: #333;
        --color-thirtytwoary: #333;
        --color-thirtythreeary: #333;
        --color-thirtyfourary: #333;
        --color-thirtyfiveary: #333;
        --color-thirtysixary: #333;
        --color-thirtysevenary: #333;
        --color-thirtyeightary: #333;
        --color-thirtynineary: #333;
        --color-fortyary: #333;
        --color-fortyoneary: #333;
        --color-fortytwoary: #333;
        --color-fortythreeary: #333;
        --color-fortyfourary: #333;
        --color-fortyfiveary: #333;

		/*		size variables */
				--sm: 640px;
				--md: 768px;
				--lg: 1024px;
				--xl: 1280px;
				--xxl: 1536px;
    }

    :global(body) {
        font-family: 'Roboto', sans-serif;
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        color: var(--color-primary);
    }



</style>