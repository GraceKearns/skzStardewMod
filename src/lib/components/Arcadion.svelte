<script lang="ts">
	import { ChevronDown } from '@lucide/svelte';
	import { slide } from 'svelte/transition';
	interface AcardionProps {
		title: string;
		isOpenByDefault: boolean;
		version: string;
		paragraph: string;
	}

	let {
		title = 'Feature Title',
		isOpenByDefault = false,
		version = '0.01',
		paragraph = 'Inner Text'
	}: AcardionProps = $props();
	let isOpen = $state(isOpenByDefault);
	function setIsOpen(value: boolean) {
		isOpen = value;
	}
</script>

<div class="content">
	<div class="heading">
		<h1 class="headingTitle">
			{title}
		</h1>
		<h2 class="headingVersion">{version}</h2>
		<button on:click={() => setIsOpen(!isOpen)} class="buttonDropDown">
			<span class="chevron-wrapper" class:rotated={isOpen}>
				<ChevronDown color="white" />
			</span>
		</button>
	</div>
	{#if isOpen}
		<div class="body" transition:slide={{ duration: 200 }}>
			<p>
				{paragraph}
			</p>
		</div>
	{/if}
</div>

<style>
	.heading {
		background-color: var(--color-darkSkzRed);
		display: flex;
		vertical-align: middle;
		align-items: center;
		justify-content:space-between;
        padding:0 1rem 0 1rem
	}
	.headingTitle {
		color: var(--color-white);
		font-size: xx-large;
	}
	.headingVersion {
		font-size: larger;
		vertical-align: middle;
		font-style: italic;
		color: white;
	}
	.buttonDropDown {
	}
	.chevron-wrapper {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		transition: transform 180ms ease;
		will-change: transform;
	}
	.chevron-wrapper.rotated {
		transform: rotate(-180deg);
	}
	.body {
        text-align: left;
        padding: 1rem;
        font-size: large;
		background-color: white;
	}
</style>
