<script>
	import { onMount } from 'svelte';

	import Nav from '../components/nav.svelte';

	let checkbox;
	const toggleDarkMode = function () {
		checkbox.checked
			? document.documentElement.classList.add('dark')
			: document.documentElement.classList.remove('dark');
	};

	onMount(() => {
		toggleDarkMode();
		checkbox.addEventListener('click', toggleDarkMode);
	});
</script>

<div class="dark:bg-gray-800 dark:text-gray-200">
	<div class="flex items-center justify-end mx-auto absolute top-3 right-3">
		<div class="flex justify-end items-center space-x-1 mx-auto relative">
			<img
				src="https://cdn0.iconfinder.com/data/icons/multimedia-line-30px/30/moon_dark_mode_night-512.png"
				alt=""
				width="24"
				height="24"
			/>
			<div>
				<input type="checkbox" name="" id="checkbox" class="hidden" bind:this={checkbox} />
				<label for="checkbox" class="cursor-pointer">
					<div class="w-9 h-5 flex items-center bg-gray-300 rounded-full p2">
						<div class="w-4 h-4 bg-white rounded-full shadow switch-ball" />
					</div>
				</label>
			</div>
		</div>
	</div>
	<div class="p-8 max-w-6xl mx-auto">
		<Nav />
		<slot />
	</div>
</div>

<style>
	@tailwind base;
	@tailwind components;
	@tailwind utilities;

	#checkbox:checked + label .switch-ball {
		transform: translateX(18px);
		transition: transform 0.2s ease-out;
	}
</style>
