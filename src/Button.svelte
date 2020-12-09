<style>
	button {
		font: inherit;
		padding: .15em 5em;
		background: orange;
		color: white;
	}

	button:hover,
	button:active {
		box-shadow: hsla(0, 0%, 0%, .25);
		cursor: pointer;
	}
</style>

<button on:click >
	<slot/>
</button>