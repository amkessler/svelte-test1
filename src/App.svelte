<script>
	export let name;
	let count = 1;

// the `$:` means 're-run whenever these values change'
$: doubled = count * 2;
$: quadrupled = doubled * 2;

function handleClick() {
	count += 1;
}
</script>

<main>
	<h1>Howdy {name}!</h1>
	<p>Testing out Svelte apps</p>
</main>

<button on:click={handleClick}>
	Count: {count}
</button>

<p>{count} * 2 = {doubled}</p>
<p>{doubled} * 2 = {quadrupled}</p>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>