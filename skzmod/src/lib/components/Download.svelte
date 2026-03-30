<script lang="ts">
	import DownloadCard from './DownloadCard.svelte';
	import SectionTitle from './SectionTitle.svelte';
    import stardewImage from '$lib/assets/images/stardewBackground.webp'

    interface ImageDataInterface {
        imageSrc:string;
        imageAlt:string;
    }
    let data:ImageDataInterface[] = [{
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    {
        imageSrc: stardewImage,
        imageAlt: "A descriptive Image"
    },
    ]
</script>

<section>
	<SectionTitle title={'Download'} color="var(--color-offBlack)" />
	<div class="content">
		<DownloadCard imageWindow={data} />
		<DownloadCard imageWindow={data} />
		<DownloadCard imageWindow={data} />
	</div>
</section>

<style>
	section {
		min-height: 70vh;
		background-color: var(--color-white);
		text-align: center;
		width: 80%;
        margin:0 auto;
	}
	.content {
		display: grid;
		grid-template-columns: repeat(3, minmax(240px, 1fr));
		grid-template-rows: repeat(3, auto);
		margin: 1.5rem auto 0;
		padding: 0 1.25rem 2rem;
        gap:1.5rem;
	}
</style>
