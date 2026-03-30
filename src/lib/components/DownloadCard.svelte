<script lang="ts">
	import ImageWindow from './ImageWindow.svelte';

	interface ImageData {
		imageSrc: string;
		imageAlt: string;
	}

	interface DownloadCardInterfaceProps {
		imageWindow: ImageData[];
	}

	let { imageWindow = [] }: DownloadCardInterfaceProps = $props();
</script>

<article>
	<div class="row row-1">
		{#each imageWindow.slice(0, 3) as image, index (index)}
			<ImageWindow imageSrc={image.imageSrc} imageAlt={image.imageAlt} />
		{/each}
	</div>
	<div class="row row-2">
		{#each imageWindow.slice(3, 6) as image, index (index)}
			<ImageWindow imageSrc={image.imageSrc} imageAlt={image.imageAlt} />
		{/each}
	</div>
	<div class="row row-3">
		{#each imageWindow.slice(6, 9) as image, index (index)}
			<ImageWindow imageSrc={image.imageSrc} imageAlt={image.imageAlt} />
		{/each}
	</div>
	<div class="row row-4">
		{#each imageWindow.slice(9, 12) as image, index (index)}
			<ImageWindow imageSrc={image.imageSrc} imageAlt={image.imageAlt} />
		{/each}
	</div>
</article>

<style>
	article {
		border: 0.25rem var(--color-skzRed) solid;
		background-color: var(--color-charcoal);
		height: 70vh;
		width: 100%;
		object-fit: cover;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		overflow: hidden;
		padding: 0;
	}

	.row {
		display: grid;
		width: 100%;
		
		justify-content: center;
		gap: 0;
	}
	.row-1 {
		grid-template-columns: minmax(320px, 400px) minmax(220px, 320px) minmax(320px, 480px);
	}
	.row-2 {
		grid-template-columns: minmax(400px, 520px) minmax(200px, 300px) minmax(220px, 320px);
	}
	.row-3 {
		grid-template-columns: minmax(220px, 320px) minmax(480px, 600px) minmax(180px, 260px);
	}
	.row-4 {
		grid-template-columns: minmax(300px, 420px) minmax(320px, 420px) minmax(200px, 320px);
	}
</style>
