<script>
    let userName = "";
    let userAge = "";
async function getWeather() {
  fetch('https://api.agify.io/?name=' + userName)
	.then((response) => response.json())
	.then((data) => {
  	userName = data.name; // Path for temperature
  	userAge = data.age; // Path for description
	});
}
</script>