<script>
	export let items = []

	$: cartTotal = items.length > 0 ? items.reduce( (sum, curVal) => {
		return sum + parseFloat(curVal.productPrice)
	}, 0): 0
	
</script>

<style>

	ul {
		list-style-type: none;
		margin: 1em;
		padding:0;
	}

	li {
		margin: .5em 0;
		padding: .5em;
		border: 1px solid #ccc;
	}

	h1 {
		font-size: 1.5rem;
		margin: 1em;
	}

</style>

<ul>
	{#if items.length === 0}
		<p>No items in cart</p>
		{:else}
		{#each items as item}
			<li>{item.productTitle} - ${item.productPrice}</li>
		{/each}
<h1>Total: ${cartTotal}</h1>
	{/if}
</ul>
