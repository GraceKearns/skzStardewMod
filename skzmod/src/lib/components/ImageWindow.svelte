<script lang="ts">
	interface ImageWindowProps {
		imageSrc: string;
		imageAlt: string;
	}
	let { imageSrc = '', imageAlt = 'A fitting description' }: ImageWindowProps = $props();
</script>

<div>
	<img src={imageSrc} alt={imageAlt} />
</div>

<style>
	div {
		height: 100%;
		width: 100%;
		border: 0.15rem solid var(--color-darkSkzRed);
		box-sizing: border-box;
	}
	img {
		height: 100%;
		width: 100%;
		display: block;
		object-fit: cover;
		image-rendering: crisp-edges;
	}
</style>
