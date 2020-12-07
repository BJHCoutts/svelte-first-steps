<script>
	export let productTitle = ''
	export let productDescription = ''
	export let productPrice = ''

</script>

<div>
	<h1>Title: {productTitle}</h1>
	<h2>Price: {productPrice}</h2>
	<p>Description: {productDescription}</p>
	<button>Add to Cart</button>
</div>

<style>
	div {
		margin: .5em;
		padding: .75em;
		box-shadow: 0 2px 8px hsla(0, 0%, 0%, .25);
		border-radius: 5px;
		background: whitesmoke;
	}

	h1 {
		font-size: 1.5rem;
		margin: 0 0 .25em;
	}

	h2 {
		font-size: 1.25rem;
		margin: 0 0 .25em;
	}

	p {
		font-size: 1rem;
		margin: 0 0 .25em;
	}

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