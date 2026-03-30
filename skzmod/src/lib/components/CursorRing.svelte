<script lang="ts">
	let x = $state(0);
	let y = $state(0);
	let isVisible = $state(false);
	let isPressed = $state(false);

	function handleMouseMove(event: MouseEvent) {
		x = event.clientX;
		y = event.clientY;
		isVisible = true;
	}

	function handleMouseDown() {
		isPressed = true;
	}

	function handleMouseUp() {
		isPressed = false;
	}

	function handleMouseLeave() {
		isVisible = false;
	}
</script>

<svelte:window
	on:mousemove={handleMouseMove}
	on:mousedown={handleMouseDown}
	on:mouseup={handleMouseUp}
	on:mouseleave={handleMouseLeave}
/>

<div
	class="cursor-ring {isVisible ? 'is-visible' : ''} {isPressed ? 'is-pressed' : ''}"
	style={`left: ${x}px; top: ${y}px;`}
	aria-hidden="true"
></div>

<style>
	.cursor-ring {
		position: fixed;
		left: 0;
		top: 0;
		width: 1.5rem;
		height: 1.5rem;
		border: 2px solid var(--color-charcoal);
		border-radius: 999px;
		pointer-events: none;
		opacity: 0;
		z-index: 9999;
		transform: translate(-50%, -50%) scale(1.2);
		transition:
			opacity 120ms ease,
			transform 140ms ease;
	}

	.cursor-ring.is-visible {
		opacity: 0.95;
	}

	.cursor-ring.is-pressed {
		transform: translate(-50%, -50%) scale(0.72);
	}

	@media (hover: none), (pointer: coarse) {
		.cursor-ring {
			display: none;
		}
	}
</style>
