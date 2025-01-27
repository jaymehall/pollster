<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import Tabs from "./shared/Tabs.svelte";

	let tabs = ["Current Polls", "Add New Poll"];
	let activeTab = "Current Polls";
</script>

<Header />
<main>
	<Tabs {tabs} {activeTab} />
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