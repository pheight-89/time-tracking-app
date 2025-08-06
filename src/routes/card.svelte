<script>
	const { title, currentTime, previousTime, iconUrl, cardClass } = $props();
</script>

<div class="card {cardClass}">
	<div class="title-icon">
		<img src={iconUrl} alt="{title} icon" />
	</div>
	<div class="cardDetails">
		<p class="title">{title}</p>
		<p class="currentTime">{currentTime}</p>
		<img class="ellipsis" src="/images/icon-ellipsis.svg" alt="ellipsis icon" />
		<p class="previousTime">{previousTime}</p>
	</div>
</div>

<style>
	.card {
		width: 350px;
		border-radius: 1rem;
		margin-block: 1.5rem;
	}

	.title-icon {
		display: flex;
		justify-content: end;
		padding-inline: 1rem;
		overflow: hidden;
		height: 30px;
	}

	.title-icon img {
		margin-top: -5px;
		height: 60px;
		overflow: hidden;
	}
	.work {
		background-color: var(--clr-work-bg);
	}

	.play {
		background-color: var(--clr-play-bg);
	}

	.study {
		background-color: var(--clr-study-bg);
	}

	.exercise {
		background-color: var(--clr-exercise-bg);
	}

	.social {
		background-color: var(--clr-social-bg);
	}

	.self-care {
		background-color: var(--clr-selfcare-bg);
	}

	.cardDetails {
		display: grid;
		grid-template-columns: 1fr 1fr;
		background-color: var(--clr-Navy900);
		padding: 2rem;
		row-gap: 1rem;
		border-radius: 1rem;
	}

	.title {
		font-size: 1.125rem;
		margin: inherit;
		font-weight: var(--fw-regular);
		color: white;
	}

	.currentTime {
		margin: inherit;
		font-size: 2rem;
		font-weight: var(--fw-thin);
		color: white;
	}

	.previousTime {
		font-size: 0.925rem;
		margin: inherit;
		justify-self: end;
		align-self: center;
		font-weight: var(--fw0-thin);
	}

	.ellipsis {
		margin: inherit;
		align-self: center;
		justify-self: end;
		grid-row-start: 1;
		grid-column: 2;
		cursor: pointer;
	}
</style>
