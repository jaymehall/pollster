<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
</script>

<Header />
<main>
	<h1>Hello World!</h1>
	<p>This is an in progresss polling app built in Svelte!</p>
</main>
<Footer />

<style>
	main {
		text-align: center;
		max-width: 960px;
		margin: 40px auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>