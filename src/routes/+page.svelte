<script>
	import Card from './card.svelte';
	import Data from '../lib/data/data.json';
	import User from './user.svelte';

	let activeFrequency = $state('weekly');

	function handleFrequencyChange(event) {
		activeFrequency = event.detail.frequency;
	}

	function currentFrequency(frequency) {
		if (frequency === 'daily') {
			return 'Day';
		} else if (frequency === 'monthly') {
			return 'Month';
		} else {
			return 'Week';
		}
	}
</script>

<main>
	<User {activeFrequency} on:frequencyChange={handleFrequencyChange} />

	{#each Data as item}
		<Card
			title={item.title}
			currentTime={`${item.timeframes[activeFrequency].current}hrs`}
			previousTime={`Last ${currentFrequency(activeFrequency)} - ${item.timeframes[activeFrequency].previous} hrs`}
			iconUrl={`/images/icon-${item.title.toLowerCase().replace(' ', '-')}.svg`}
			cardClass={item.title.toLowerCase().replace(' ', '-')}
		/>
	{/each}
</main>

<style>
	main {
		display: grid;
		flex-wrap: wrap;
		justify-content: center;
		align-items: flex-start;
		padding: 1.5rem;
		margin: 0 auto;
		align-content: center;
	}
</style>
