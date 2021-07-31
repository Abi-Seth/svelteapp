<script>
    import { createEventDispatcher } from 'svelte'

    let dispatch = createEventDispatcher();

    let name;
    let beltColor;
    let age;

    let fighting = false;
    let running = false;
    let sneaking = false;

    let skills = [];

    const handleForms = () => {
        const person = {
            name: name,
            beltColor: beltColor,
            age: age,
            skills: skills,
            id: Math.random()
        }

        dispatch('addPerson', person);

        console.warn(name, beltColor, age, fighting, running, sneaking, skills);
    }
</script>

<form on:submit|preventDefault={handleForms}>
    <input type="text" placeholder="Enter name" bind:value={name}>
    <input type="text" placeholder="Enter belt color" bind:value={beltColor}>
    <input type="number" placeholder="Enter age" bind:value={age}>
    <h4>Skills:</h4>
    <input type="checkbox" bind:checked={fighting}>Fighting <br>
    <input type="checkbox" bind:checked={running}>Running <br>
    <input type="checkbox" bind:checked={sneaking}>Sneaking <br>
    <p>other way.....</p>
    <input type="checkbox" bind:group={skills} value="fighting">Fighting <br>
    <input type="checkbox" bind:group={skills} value="running">Running <br>
    <input type="checkbox" bind:group={skills} value="sneaking">Sneaking <br>
    <h4>Select belt color</h4>
    <select bind:value={beltColor}>
        <option value="black">black</option>
        <option value="blue">blue</option>
        <option value="red">red</option>
        <option value="white">white</option>
    </select>
    <button>Add person</button>
</form>

<style>

</style>