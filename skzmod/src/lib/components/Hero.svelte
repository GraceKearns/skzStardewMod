<script lang="ts">
	import skzLogo from '$lib/assets/images/skzLogo.png';
	import stardewBackground from '$lib/assets/images/stardewBackground.webp';
</script>

<section class="hero" style:--hero-image={`url(${stardewBackground})`}>
	<div class="overlay"></div>
	<div class="content">
		<img src={skzLogo} alt="SKZ Logo"/>
		<p>Your favourite boys, in your favourite game.</p>
	</div>
</section>

<style>
	.hero {
		position: relative;
		min-height: 70vh;
		display: grid;
		place-items: center;
		background-image: var(--hero-image);
		background-size: cover;
		background-position: center;
		overflow: hidden;
	}
	.overlay {
		position: absolute;
		inset: 0;
		background: radial-gradient(circle at center, rgb(255 255 255 / 78%) 0%, rgb(255 255 255 / 72%) 100%);
	}
	.content {
		position: relative;
		z-index: 1;
		text-align: center;
		padding: 2rem;
		color: var(--color-softWhite);
	}
	.content img {
		display: block;
		margin: 0 auto;
		width: clamp(240px, 60vw, 90vw);
		height: auto;
	}
	p {
        color:var(--color-charcoal);
		margin: 0;
		font-size: clamp(1rem, 2.5vw, 1.25rem);
	}
</style>
