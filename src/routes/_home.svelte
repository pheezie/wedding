<script>
	import Section from '$lib/section.svelte';
	import Scroller from '$lib/scroller.svelte';

	import { title } from '$lib/store.js';
</script>

<Section bgi="bg1" blend={false} id="one">
	<div class="subject">
		<img class="pic" src="/image/pic7.jpg" alt="title" />
		<img class="flower" src="image/f1.png" alt="flower1" />
		<img class="bird" src="image/f2.png" alt="bird" />
	</div>

	<h1>{$title}</h1>

	<Scroller id="two" />
</Section>

<style>
	.subject {
		--imagePad: 60px;
		--imgMaxSize: 400px;

		position: relative;

		width: calc(100vw - var(--imagePad));
		height: calc(100vw - var(--imagePad));

		max-width: var(--imgMaxSize);
		max-height: var(--imgMaxSize);

		margin: 0 auto;

		overflow: hidden;
	}
	img {
		position: absolute;
	}
	h1 {
		color: var(--fColor1);
		font-size: 4em;
		text-shadow: 0 0 3px var(--color3), 0 0 3px var(--color3), 0 0 3px var(--color3);
	}
	.pic {
		top: 12.5%;
		left: 12.5%;

		width: 75%;
		height: 75%;

		object-fit: cover;
		border-radius: 50%;
	}
	.flower {
		top: 2.5%;
		left: 2.5%;

		width: 95%;
		height: 95%;

		animation-name: revolve;
		animation-duration: 250s;
		animation-iteration-count: infinite;
		animation-timing-function: linear;
	}
	.bird {
		bottom: 15%;
		right: 15%;

		width: 20%;
		height: 20%;
	}

	@keyframes revolve {
		from {
			transform: rotateZ(0);
		}
		to {
			transform: rotateZ(360deg);
		}
	}

	@media screen and (min-width: 800px) {
		.subject {
			--imgMaxSize: 450px;
		}
	}
	@media screen and (min-width: 1200px) {
		.subject {
			--imgMaxSize: 500px;
		}
	}
</style>
