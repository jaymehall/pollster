<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import Tabs from "./shared/Tabs.svelte";
	import CreatePollForm from "./components/CreatePollForm.svelte";

	let tabs = ["Current Polls", "Add New Poll"];
	let activeTab = "Current Polls";

	const tabChange = (e) => {
		activeTab = e.detail;
	}
</script>

<Header />
<main>
	<Tabs {tabs} {activeTab} on:tabChange={tabChange}/>
	{#if activeTab === "Current Polls"}
		<p>Poll list component goes here</p>
	{:else if activeTab === "Add New Poll"}
		<CreatePollForm />
	{/if}
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