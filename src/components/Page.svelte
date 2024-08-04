<script lang="ts">

	import { PageSizes } from '../models/PageSizes';
	import { PageLayouts } from '../models/PageLayouts';


	export let size: PageSizes = PageSizes.A4;
	export let layout: PageLayouts = PageLayouts.Portrait;
	let uuid = crypto.randomUUID();
	let page: HTMLElement | null;

</script>

<page id={uuid} size={size} layout={layout} bind:this={page}>
	<slot></slot>
</page>

<style>
    page {
        background: white;
        display: block;
				flex-direction: column;
        margin: 0 auto 0.5cm;
        box-shadow: 0 0 0.5cm rgba(0, 0, 0, 0.5);
        position: relative;
    }

    page[size="A4"] {
        width: 793px;
				height: 1122px;
	}

    page[size="A4"][layout="landscape"] {
        width: 29.7cm;
        height: 21cm;
    }

    page[size="A3"] {
        width: 29.7cm;
        height: 42cm;
    }

    page[size="A3"][layout="landscape"] {
        width: 42cm;
        height: 29.7cm;
    }

    page[size="A5"] {
        width: 14.8cm;
        height: 21cm;
    }

    page[size="A5"][layout="landscape"] {
        width: 21cm;
        height: 14.8cm;
    }

    @media print {
        :global(body, page) {
            background: white;
            margin: 0;
            box-shadow: unset;
        }
    }
</style>