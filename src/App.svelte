<script>
	let name = 'Kwizera Caleb';
	let beltColor = 'black';

	const handleClick = () => {
		beltColor = 'orange'
	}

	const handleEventBind = (e) => {
		beltColor = e.target.value;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {beltColor};">Learning in {beltColor}.</p>
	<button on:click={handleClick}>Change class</button>
	<input type="text" on:input={handleEventBind} value={beltColor}>
	<input type="text" bind:value={beltColor}> 
</main>

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