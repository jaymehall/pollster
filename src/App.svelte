<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import Tabs from "./shared/Tabs.svelte";
	import CreatePollForm from "./components/CreatePollForm.svelte";
	import PollList from "./components/PollList.svelte";

	let tabs = ["Current Polls", "Add New Poll"];
	let activeTab = "Current Polls";

	const tabChange = (e) => {
		activeTab = e.detail;
	}

	let polls = [
		{
			id: 1,
			question: "Svelte or React?",
			answerA: "Svelte",
			answerB: "React",
			votesA: 100,
			votesB: 10,
		}
	];

	const handleAddPoll = (e) => {
		const poll = e.detail;
		polls = [poll, ...polls];
		activeTab = "Current Polls";
	}
</script>

<Header />
<main>
	<Tabs {tabs} {activeTab} on:tabChange={tabChange}/>
	{#if activeTab === "Current Polls"}
		<PollList {polls} />
	{:else if activeTab === "Add New Poll"}
		<CreatePollForm on:add={handleAddPoll} />
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