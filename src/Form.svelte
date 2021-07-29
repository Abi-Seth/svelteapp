<script>
    let name;
    let beltColor;
    let age;

    const handleForms = () => {
        console.warn(name, beltColor, age);
    }
</script>

<form on:submit|preventDefault={handleForms}>
    <input type="text" placeholder="Enter name" bind:value={name}>
    <input type="text" placeholder="Enter belt color" bind:value={beltColor}>
    <input type="number" placeholder="Enter age" bind:value={age}>
    <button>Add person</button>
</form>

<style>

</style>