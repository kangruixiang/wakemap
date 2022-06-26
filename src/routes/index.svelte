<script>
	import { Motion } from 'svelte-motion';
	import Spots from '../lib/Spots.svelte';
	let floors = [
		'Floor SB.png',
		'Floor M.png',
		'Floor G.png',
		'Floor 1.png',
		'Floor 2.png',
		'Floor 3.png',
		'Floor 4.png',
		'Floor 5.png',
		'Floor 6.png',
		'Floor 7.png',
		'Floor 8.png',
		'Floor 9.png',
		'Floor 10.png',
		'Floor 11.png'
	];
	let floor = 0;
	$: floor > 13 ? (floor = 13) : (floor = floor);
	$: floor < 0 ? (floor = 0) : (floor = floor);
	$: console.log(floor);
</script>

<main
	class="h-screen w-screen bg-zinc-800 md:items-center md:justify-center flex overflow-y-auto flex-col pt-24"
>
	<div class="md:px-8 flex flex-col">
		<div class="">
			<img src={floors[floor]} alt="map" class="border-none" />
		</div>
		<div class="mt-4 flex items-center justify-center space-x-32">
			<Motion whileTap={{ scale: 0.99 }} let:motion>
				<button use:motion class="btn" on:click={() => (floor = floor -= 1)}>Go Down</button>
			</Motion>
			<Motion whileTap={{ scale: 0.99 }} let:motion>
				<button use:motion class="btn" on:click={() => (floor = floor += 1)}>Go Up</button>
			</Motion>
		</div>
	</div>
</main>

<style>
</style>
