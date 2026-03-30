<nav>
	<ul class="">
		<li><a href="/">Home</a></li>
		<li><a href="/download">Download</a></li>
		<li><a href="/images">Images</a></li>
		<li><a href="/credits">Credits</a></li>
		<li><a href="/changelog">Changelog</a></li>
	</ul>
</nav>

<style>
	nav {
		transform: scaleX(0); 
		transform-origin: left center;
		animation: navGrow 0.2s ease-out forwards;
		background-color: var(--color-skzRed);
	}
	ul {
		list-style: none;
		display: flex;
		justify-content: end;
		gap: 1rem;
		margin-right: 10%;
		padding-top: 1rem;
		padding-bottom: 1rem;
		align-items: center;
	}

	a {
		color: var(--color-softWhite);
		text-decoration: none;
		font-weight: 600;
		font-size: 2rem;
		padding: 0.35rem 0.55rem;
		padding-top: 1rem;
		padding-bottom: 1rem;
		border-radius: 0.4rem;
		transition:
			background-color 0.2s ease,
			color 0.2s ease;
	}
	@keyframes navGrow {
		from {
			transform: scaleX(0);
			opacity: 0.7;
		}

		to {
			transform: scaleX(1);
			opacity: 1;
		}
	}
	a:hover {
		background: var(--color-darkSkzRed);
		color: var(--color-white);
	}
</style>
