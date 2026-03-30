<script lang="ts">
	import StardewCard from './StardewCard.svelte';
	import stardewBackground from '$lib/assets/images/stardewBackground.webp';
	import SectionTitle from './SectionTitle.svelte';
</script>

<section>
	<SectionTitle title="Mod Features" color="var(--color-white)"/>
	<div class="content">
		<StardewCard
			title="Meet The Boys"
			description="Find every Stray Kids member around Stardew Valley, each with unique dialogue and personality."
			imageSrc={stardewBackground}
			imageAlt="Stardew valley farm background"
		/>
		<StardewCard
			title="Stay Hotel"
			description="Check into a brand-new area designed for fan encounters, surprises, and special interactions."
			imageSrc={stardewBackground}
			imageAlt="Stardew valley seasonal event"
		/>
		<StardewCard
			title="Custom Portraits"
			description="Enjoy polished portraits and expressive art that make every conversation feel alive."
			imageSrc={stardewBackground}
			imageAlt="Stardew valley custom portraits"
		/>
		<StardewCard
			title="Heart Storylines"
			description="Unlock deeper story paths as your bonds grow through quests, events, and shared farm moments."
			imageSrc={stardewBackground}
			imageAlt="Stardew valley heart events"
		/>
	</div>
</section>

<style>
	section {
		background-size: cover;
		position: relative;
		background-color: var(--color-offBlack);
		width: 100%;
		min-height: 70vh;
		text-align: center;
	}
	.content {
		display: grid;
		grid-template-columns: repeat(2, minmax(240px, 1fr));
		grid-template-rows: repeat(2, auto);
		gap: 1.75rem;
		width: calc(70vw * 0.6);
		margin: 1.5rem auto 0;
		padding: 0 1.25rem 2rem;
	}

	@media (max-width: 1376px) {
		.content {
			width: calc(100vw * 0.8);
		}
	}

	@media (max-width: 840px) {
		.content {
			width: calc(100vw * 0.8);
			grid-template-columns: 1fr;
			grid-template-rows: auto;
		}
	}
</style>
