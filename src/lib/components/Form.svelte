<script>
	let min = $state(0);
	let max = $state(10);
	let random = $derived(Math.floor(Math.random() * max));

	function oninputmin(event) {
		console.log(event.data);
		min = event.data;
	}
	function oninputmax(event) {
		console.log(event.data);
		max = event.data;
	}
</script>

<label for="min">Min</label>
<input type="number" name="min" id="min" oninput={oninputmin} />
<label for="max">Max</label>
<input type="number" name="max" id="max" oninput={oninputmax} />
<h1>{random}</h1>

<style></style>
