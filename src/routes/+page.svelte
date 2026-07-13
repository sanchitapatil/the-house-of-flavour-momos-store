<script>
	import Hero from '$lib/components/Hero.svelte';
	import Story from '$lib/components/Story.svelte';
	import Philosophy from '$lib/components/Philosophy.svelte';
	import Menu from '$lib/components/Menu.svelte';
	import ProductSpotlight from '$lib/components/ProductSpotlight.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
	<title>House of Flavour | Premium Homemade Momos</title>
	<meta name="description" content="Pure veg, authentic homemade momos freshly prepared daily in small batches. Served with our famous Chilli Charm Garlic Chutney. Order now from our Wakad branch!" />
	<meta name="keywords" content="momos, pure veg momos, house of flavour, chilli charm chutney, wakad street food, homemade momos, kurkure momos, peri-peri momos" />
	
	<!-- OpenGraph / Social Meta Tags -->
	<meta property="og:title" content="House of Flavour | Flavour That Speaks" />
	<meta property="og:description" content="Premium, pure vegetarian homemade momos and signature Chilli Charm Chutney. Find our cart in Wakad!" />
	<meta property="og:type" content="website" />
</svelte:head>

<main class="w-full overflow-x-hidden selection:bg-[var(--color-hof-red)] selection:text-white">
	<Hero />
	<Story />
	<Philosophy />
	<Menu />
	<ProductSpotlight />
	<Footer />
</main>
