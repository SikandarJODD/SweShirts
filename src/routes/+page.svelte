<script>
	import PageHero from '$lib/PageHero.svelte';
	import PageDown from '../lib/PageDown.svelte';
	import ProductSub from '../lib/ProductSub.svelte';
	let value = 23;
</script>

<svelte:head>
	<title>Sweat Shirts</title>
	<meta name="description" content="Cool Sweatshirts For Youth, High Quality T-Shirts  " />
	<link
		rel="icon"
		href="https://cdn-icons-png.flaticon.com/512/5499/5499091.png"
		type="image/x-icon"
	/>

	<meta
		name="og:image"
		itemprop="image"
		content="https://cdn-icons-png.flaticon.com/512/5499/5499091.png"
	/>
</svelte:head>

<main>
	<PageHero />
	<ProductSub />
	<!-- <PageDown /> -->
	<!-- <h1 class="text-3xl font-bold text-center text-slate-200">Fusion XD</h1> -->
</main>

<style lang="postcss">
	:global(html) {
		/* background-color: theme(colors.gray.100) !important; */
	}
</style>
