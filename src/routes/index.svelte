<script>
    let userName = "";
    let userAge = "";
async function getAge() {
  fetch('https://api.agify.io/?name=' + userName)
	.then((response) => response.json())
	.then((data) => {
  	userName = data.name; 
  	userAge = data.age; 
	});
}
</script>

<h1>Guess Age App</h1>

<form on:submit|preventDefault={getAge}>
    <label for="name">Name:</label>
    <input id="userName" bind:value={userName} type="text" />
    <button type="submit">Check</button>
</form>
<p>Age:{userAge}</p>
