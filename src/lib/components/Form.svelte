<script>
	let min = $state(0);
	let max = $state(10);
	let placeholder = $derived(Math.floor(Math.random() * (max - min + 1)) + min);

	function oninputmin(event) {
		min = +event.target.value;
		console.log(min);
	}
	function oninputmax(event) {
		max = +event.target.value;
		console.log(max);
	}

	function onclick() {
		console.log(`Min: ${min}, Max: ${max}`);
		// placeholder = Math.floor(Math.random() * (max - min + 1)) + min;
		console.log(placeholder);
	}
</script>

<p>Generate a random number</p>

<form class="w-full max-w-lg">
	<div class="-mx-3 mb-6 flex flex-wrap">
		<div class="mb-6 w-full px-3 md:mb-0 md:w-1/2">
			<label class="mb-2 block text-xs font-bold uppercase tracking-wide text-gray-700" for="min">
				Min. Value
			</label>
			<input
				class="mb-3 block w-full appearance-none rounded border border-red-500 bg-gray-200 px-4 py-3 leading-tight text-gray-700 focus:bg-white focus:outline-none"
				id="min"
				type="number"
				placeholder="Min value"
				onchange={oninputmin}
			/>
		</div>
		<div class="w-full px-3 md:w-1/2">
			<label
				class="mb-2 block text-xs font-bold uppercase tracking-wide text-gray-700"
				for="grid-last-name"
			>
				Max. value
			</label>
			<input
				class="block w-full appearance-none rounded border border-gray-200 bg-gray-200 px-4 py-3 leading-tight text-gray-700 focus:border-gray-500 focus:bg-white focus:outline-none"
				id="grid-last-name"
				type="number"
				placeholder="Max. Value"
				onchange={oninputmax}
			/>
		</div>
	</div>
</form>

<h1 class="">The random number is: {placeholder}</h1>

<style>
</style>
