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
			id: -1,
			question: "Svelte or React?",
			answerA: "Svelte",
			answerB: "React",
			votesA: 100,
			votesB: 10,
		},
		{
			id: 0,
			question: "Hello...?",
			answerA: "World!",
			answerB: "Huh?",
			votesA: 70,
			votesB: 30,
		}
	];

	const handleAddPoll = (e) => {
		const poll = e.detail;
		polls = [poll, ...polls];
		activeTab = "Current Polls";
	}

	const handleVote = (e) => {
		const {id, option} = e.detail;
		let copiedPolls = [...polls];
		const votedPoll = copiedPolls.find((poll) => poll.id === id);
		if(votedPoll) {
			if(option === 'a') {
				votedPoll.votesA++
			}
			if(option === 'b') {
				votedPoll.votesB++
			}
		}

		polls = copiedPolls;
	}
</script>

<Header />
<main>
	<Tabs {tabs} {activeTab} on:tabChange={tabChange}/>
	{#if activeTab === "Current Polls"}
		<PollList {polls} on:vote={handleVote} />
	{:else if activeTab === "Add New Poll"}
		<CreatePollForm on:add={handleAddPoll} />
	{/if}
</main>
<Footer />

<style>
	main {
		text-align: center;
		max-width: 960px !important;
		margin: 40px auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>