<script>

	export let productTitle = ''
	export let productDescription = ''
	export let productPrice = ''
	
	import Button from './Button.svelte'
	import { createEventDispatcher } from 'svelte'

	const dispatch = createEventDispatcher()

	const addToCart = () => {
		dispatch('addcart', productTitle)
	}
	
</script>

<style>

	div {
		margin: .5em;
		padding: .75em;
		box-shadow: 0 2px 8px hsla(0, 0%, 0%, .25);
		border-radius: 5px;
		background: hsla( 0, 0%, 97%, 1);
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

</style>

<div>
	<h1>Title: {productTitle}</h1>
	<h2>Price: {productPrice}</h2>
	<p>Description: {productDescription}</p>
	<Button on:click={addToCart}>Add to Cart</Button>
</div>
