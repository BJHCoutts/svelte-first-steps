<script lang="ts">
	export let name: string
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

</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

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

</section>

<Product productTitle={productTitle} productDescription={productDescription} productPrice={productPrice}/>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
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
		margin: 3em auto;
	}

</style>