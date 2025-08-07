<script>
	const { title, currentTime, previousTime, iconUrl, cardClass } = $props();
</script>

<div class="card {cardClass}">
	<div class="title-icon">
		<img src={iconUrl} alt="{title} icon" />
	</div>
	<div class="cardDetails">
		<div class="header-row">
			<p class="title">{title}</p>
			<img class="ellipsis" src="/images/icon-ellipsis.svg" alt="ellipsis icon" />
		</div>
		<div class="time-row">
			<p class="currentTime">{currentTime}</p>
			<p class="previousTime">{previousTime}</p>
		</div>
	</div>
</div>

<style>
	.card {
		width: 20.5rem;
		max-width: 100%;
		border-radius: 1rem;
		overflow: hidden;
	}

	.title-icon {
		display: flex;
		justify-content: flex-end;
		padding-right: 1rem;
		height: 2.5rem;
		overflow: hidden;
	}

	.title-icon img {
		margin-top: -10px;
		height: 5rem;
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
		display: flex;
		flex-direction: column;
		background-color: var(--clr-Navy900);
		padding: 2rem;
		border-radius: 1rem;
		gap: 0.5rem;
	}

	.header-row,
	.time-row {
		display: flex;
		justify-content: space-between;
		align-items: center;
		flex-wrap: wrap;
	}

	.title {
		font-size: 1.125rem;
		margin: 0;
		font-weight: var(--fw-regular);
		color: white;
	}

	.currentTime {
		margin: 0;
		font-size: 2rem;
		font-weight: var(--fw-thin);
		color: white;
	}

	.previousTime {
		margin: 0;
		font-weight: var(--fw-thin);
	}

	.ellipsis {
		margin: 0;
		height: 8px;
		cursor: pointer;
	}
</style>
