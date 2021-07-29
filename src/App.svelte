<script>
	let name = 'Kwizera Caleb';
	let beltColor = 'black';

	const handleClick = () => {
		beltColor = 'orange'
	}

	const handleEventBind = (e) => {
		beltColor = e.target.value;
	}

	//reactive values 
	let firstname = 'Abijuru';
	let lastname = 'Seth';

	$: firstname;
	$: lastname;

	$: fullnames = `${firstname} ${lastname}`;

	$: console.warn(firstname);

	$: {
		console.log(firstname);
		console.log(lastname);
	}

	//loops
	let people = [
		{name: 'Seth', beltColor: 'yellow', age: 12, id: 1},
		{name: 'Yoshi', beltColor: 'black', age: 18, id: 2},
		{name: 'Abi', beltColor: 'blue', age: 42, id: 3},
	]

	const deletePerson = (event, id) => {
		people = people.filter((person) => person.id != id);
		console.log(event);
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {beltColor};">Learning in {beltColor}.</p>
	<button on:click={handleClick}>Change class</button>
	<input type="text" on:input={handleEventBind} value={beltColor}>
	<input type="text" bind:value={beltColor}> 

	<h3>Reactive svelte values</h3>
	<p>{fullnames} - {beltColor} belt</p>
	<input type="text" bind:value={firstname}>
	<input type="text" bind:value={lastname}>

	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			<p>{person.beltColor} belt - {person.age} years old.</p>
			<button on:click={(event) => deletePerson(event, person.id)}>delete</button>
		</div>
	{:else}
		<p>No person registered yet.</p>
	{/each}
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