<script lang="ts">
	export let name: string
	import Button from './Button.svelte'
	import Product from './Product.svelte'
	
	let productTitle = ''
	let productPrice = ''
	let productDescription = ''
	
	const setProductTitle = (e: Event) => {
		productTitle = (e.target as HTMLInputElement).value
	}
	const setProductPrice = (e: Event) => {
		productPrice = (e.target as HTMLInputElement).value
	}
	const setProductDescription = (e: Event) => {
		productDescription = (e.target as HTMLInputElement).value
	}
	
	let products = []
	let cartItems = []
	
	const createProduct = () => {
		const newProduct = {
			productTitle,
			productPrice,
			productDescription, 
		}
		products = products.concat(newProduct)
	}

	const addToCart = (event) => {
		const selectedTitle = event.detail
		cartItems = cartItems.concat(
			{...products.find(prod => prod.productTitle === selectedTitle)}
		)
		console.log(cartItems)
	}
	
</script>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		background: hsla(0, 0%, 90%, 1);
	}

	h1 {
		color: purple;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	label {
		cursor: pointer;
		margin: 0 0 .25em;
	}

	section {
		margin: 0 auto;
		width: 30em;
	}

</style>

<main>

	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	
	<section>
	
		<div>
			<label for='productTitle' >Title</label>
			<input type='text' name='productTitle' id='productTitle' bind:value={productTitle} on:input={setProductTitle} />
		</div>
		
		<div>
			<label for='price' >Price</label>
			<input type='number' name='productPrice' id='productPrice' bind:value={productPrice} on:input={setProductPrice} />
		</div>
		
		<div>
			<label for='description' >Description</label>
			<textarea rows='4' name='productDescription' id='productDescription' bind:value={productDescription} on:input={setProductDescription} />
		</div>

		<Button on:click={createProduct} >Create Product</Button>

	</section>

	<section>
		{#if products.length===0}
			<p>No products added yet</p>
			{:else}
			{#each products as product}
			<Product 
				productTitle={product.productTitle} 
				productDescription={product.productDescription} 
				productPrice={product.productPrice}
				on:addcart={addToCart}
			/>
			{/each}
		{/if}
	</section>


</main>