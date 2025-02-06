<script>
	let min = $state(0);
	let max = $state(10);
	let placeholder = $derived(Math.floor(Math.random() * (max - min + 1)) + min);
	let click = $state(false);
	let number = $state(0);

	function oninputmin(event) {
		click = false;
		min = +event.target.value;
		console.log(min);
	}
	function oninputmax(event) {
		click = false;
		max = +event.target.value;
		console.log(max);
	}

	function onclick() {
		console.log(`Min: ${min}, Max: ${max}`);
		click = true;
		number = Math.floor(Math.random() * (max - min + 1)) + min;
		return number;
	}
</script>

<div class="m-8">
	<p class="text-lg">Random number generator</p>

	<form class=" w-full max-w-lg">
		<div class="-mx-3 mb-6 flex flex-wrap">
			<div class="mb-6 w-full px-3 md:mb-0 md:w-1/2">
				<label class="mb-2 block text-xs font-bold uppercase tracking-wide text-gray-700" for="min">
					Min. Value
				</label>
				<input
					class="mb-3 block w-full appearance-none rounded border border-red-500 bg-gray-200 px-4 py-3 leading-tight text-gray-700 focus:bg-white focus:outline-none"
					id="min"
					type="number"
					placeholder="Default = 0"
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
					placeholder="Default = 10"
					onchange={oninputmax}
				/>
			</div>
		</div>
	</form>
	<button class="rounded bg-blue-500 px-4 py-2 font-bold text-white hover:bg-blue-700" {onclick}
		>Run</button
	>

	<h1 class="text-lg">
		The random number is: <span class="font-extrabold">{click == true ? number : placeholder}</span>
	</h1>
</div>

<style>
</style>
