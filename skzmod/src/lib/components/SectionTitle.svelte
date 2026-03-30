<script lang="ts">
	interface SectionTitleProps {
		title?: string;
		color?: string;
	}
	let { title = 'Feature Title', color = '#ffffff' }: SectionTitleProps = $props();
</script>

<h1 style={`color: ${color};`}>{title}</h1>
<hr/>

<style>
	h1 {
		font-size: 4rem;
		margin: 0;
        text-align: center;
	}
	hr {
		border-top: 1rem solid var(--color-darkSkzRed);
		width: 50%;
		margin:0 auto;
		min-height: 4vh;
	}
</style>
