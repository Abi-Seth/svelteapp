<script>
    let name;
    let beltColor;
    let age;

    let fighting = false;
    let running = false;
    let sneaking = false;

    let skills = [];

    const handleForms = () => {
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
    
    <button>Add person</button>
</form>

<style>

</style>