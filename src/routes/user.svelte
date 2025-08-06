<script>
	const { activeFrequency } = $props();

	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	function handleClick(frequency) {
		dispatch('frequencyChange', { frequency });
	}
</script>

<div class="userCard">
	<div class="userContainer">
		<div class="userImage">
			<img class="profilePicture" src="/images/image-jeremy.png" alt="profile picture" />
		</div>
		<div class="userDetails">
			<p>Report for</p>
			<p>Jeremy Robson</p>
		</div>
	</div>
	<div class="frequencySelector">
		<button
			class="frequencyBtn"
			class:active={activeFrequency === 'daily'}
			onclick={() => handleClick('daily')}>Daily</button
		>

		<button
			class="frequencyBtn"
			class:active={activeFrequency === 'weekly'}
			onclick={() => handleClick('weekly')}>Weekly</button
		>

		<button
			class="frequencyBtn"
			class:active={activeFrequency === 'monthly'}
			onclick={() => handleClick('monthly')}>Monthly</button
		>
	</div>
</div>

<style>
	.userCard {
		width: 350px;
		display: grid;
		background-color: var(--clr-Navy900);
		border-radius: 1rem;
		overflow: hidden;
	}

	.userContainer {
		display: flex;
		background-color: var(--clr-purple600);
		gap: 1rem;
		padding: 2rem 2rem;
		border-radius: 1rem;
	}

	.profilePicture {
		height: 60px;
		border: solid 3px white;
		border-radius: 50%;
	}

	.userDetails {
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
	.userDetails p {
		margin: 0;
	}

	.userDetails p:nth-child(2) {
		font-size: 1.5rem;
		color: white;
	}

	.frequencySelector {
		display: flex;
		padding-block: 1rem;
		justify-content: space-evenly;
	}

	.frequencyBtn {
		border: none;
		background-color: transparent;
		color: var(--clr-Purple500);
		cursor: pointer;
		font-size: 1.125rem;
	}

	.active {
		color: white;
	}
</style>
