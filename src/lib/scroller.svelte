<script>
	export let text = 'Scroll';
	export let id;

	const scrollTo = () => {
		let e = document.querySelector(`#${id}`);
		e.scrollIntoView({
			behavior: 'smooth'
		});
	};
</script>

<div class="scroller" on:click={scrollTo}>
	<div class="mouse" />
	<div class="wheel" />
	{text}
</div>

<style>
	.scroller {
		display: flex;
		flex-direction: column;
		align-items: center;

		position: absolute;
		bottom: 20px;
		right: 20px;

		color: var(--fColor1);

		cursor: pointer;
	}
	@media screen and (min-width: 800px) {
		.scroller {
			display: none;
		}
	}
	.mouse {
		width: 25px;
		height: 35px;

		border: 2px solid var(--color1);
		border-radius: calc(25px / 2);
	}
	.wheel {
		position: absolute;
		top: 5px;

		border: 2px solid var(--color1);
		border-radius: calc(25px / 2);

		animation-name: scroll;
		animation-duration: 1s;
		animation-iteration-count: infinite;
		animation-timing-function: cubic-bezier();
		animation-direction: alternate-reverse;
	}

	@keyframes scroll {
		from {
			height: 0px;
		}
		to {
			height: 10px;
		}
	}
</style>
