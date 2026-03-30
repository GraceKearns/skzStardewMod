<script>
	import Arcadion from '$lib/components/Arcadion.svelte';
	import SectionTitle from '$lib/components/SectionTitle.svelte';
	import StardewCard from '$lib/components/StardewCard.svelte';
</script>

<section>
	<SectionTitle title={'Download'} color={'var(--color-white)'} />
	<div class="content">
		<div class="updateLogs">
            <SectionTitle title={"Update Logs"} color={"var(--color-white)"}/>
            <Arcadion title={"Title"} paragraph={"Hello Im paragraph"} isOpenByDefault={true} version={"0.01"} />
        </div>
		<StardewCard title={'Download'} description={'Click here to download the latest version of the modpack'} />
	</div>
</section>

<style>
	section {
		background-color: var(--color-charcoal);
		display: flex;
		flex: 1 1 auto;
		flex-direction: column;
		width: 100%;
		text-align: center;
	}
	.content {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: 1fr auto;
		gap: 1.75rem;
		width: calc(70vw * 0.6);
		margin: 0 auto;
        align-items: start;
	}
    .updateLogs {
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
       
    }
</style>
