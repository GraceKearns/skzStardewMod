<script lang="ts">
	interface CardProps {
		title?: string;
		description?: string;
		imageSrc?: string;
		imageAlt?: string;
		tag?: string;
	}

	let {
		title = 'Feature Title',
		description = 'Short description of this feature.',
		imageSrc = '',
		imageAlt = 'Feature image',
		tag = 'Feature'
	}: CardProps = $props();
</script>

<article class="card">
	<div class="card__pulse" aria-hidden="true"></div>
	<h2 class="cardTitle">{title}</h2>
	{#if imageSrc}
		<img class="card__image" src={imageSrc} alt={imageAlt} />
	{/if}
	<p class="cardDescription">{description}</p>
</article>

<style>
	.card {
		position: relative;
		background: linear-gradient(165deg, var(--color-charcoal) 0%, var(--color-offBlack) 100%);
		border: 0.14rem solid var(--color-darkSkzRed);
		padding: 3.5rem 1.2rem 1.25rem;
		overflow: hidden;
		transition:
			transform 180ms ease,
			box-shadow 180ms ease;
		box-shadow:
			0 14px 28px rgb(0 0 0 / 35%),
			0 0 0 1px rgb(165 60 64 / 30%);
        cursor:pointer;
	}
	.card:hover {
		transform: translateY(-8px);
		box-shadow:
			0 18px 34px rgb(0 0 0 / 42%),
			0 0 0 1px rgb(165 60 64 / 46%);
	}
	@keyframes slide-in {
		from {
			transform: translateX(0%);
		}

		to {
			transform: translateX(100%);
		}
	}
	.card::before {
		content: '';
		position: absolute;
		inset: auto 0 0 0;
		height: 1rem;
		background: linear-gradient(var(--color-skzRed), var(--color-darkSkzRed));
	}

	.card__pulse {
		position: absolute;
		top: -4rem;
		right: -2rem;
		width: 30rem;
		height: 30rem;
		border-radius: 50%;
		background: radial-gradient(circle, rgb(165 60 64 / 50%) 0%, rgb(165 60 64 / 0%) 70%);
		pointer-events: none;
	}

	.card__image {
		width: 100%;
		height: 50%;
		object-fit: cover;
		object-position: bottom;
		border: 1px solid rgb(255 255 255 / 18%);
		border-radius: 0.45rem;
		margin-bottom: 0.8rem;
	}

	.cardTitle {
		position: absolute;
		top: 0rem;
		left: 0rem;
		margin: 0;
		padding: 0.32rem 0.68rem;
		background: var(--color-skzRed);
		color: var(--color-softWhite);
		border: 1px solid var(--color-darkSkzRed);
		font-size: 2rem;
		font-weight: 700;
		letter-spacing: 0.03em;
		line-height: 1.15;
		text-transform: uppercase;
	}

	.cardDescription {
		margin: 0;
		color: var(--color-softWhite);
		line-height: 1.5;
		height: auto;
		font-size: 1.5rem;
	}
</style>
