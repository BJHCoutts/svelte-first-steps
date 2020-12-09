<script>
	export let items

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
	{#each items as item}
		<li>{item.productTitle} - {item.productPrice}</li>
	{/each}
</ul>

<h1>Total: </h1>