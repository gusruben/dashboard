<script lang="ts">
	import Icon from "@iconify/svelte";

	let searchInput = "";
	let isFocused = false;

	function handleSearch(event: KeyboardEvent) {
		if (event.key === 'Enter' && searchInput.trim()) {
			const query = encodeURIComponent(searchInput.trim());
			window.open(`https://duckduckgo.com/?q=${query}`, '_blank');
		}
	}
</script>

<!-- svelte-ignore a11y_click_events_have_key_events -->
<div 
	class="col-span-7 row-span-1 flex items-center rounded-3xl bg-gray-900 transition-all duration-200 overflow-hidden hover:bg-gray-850"
	class:focused={isFocused}
	role="button"
	tabindex="0"
>
	<div class="flex-shrink-0 h-full p-5 cursor-pointer group">
		<Icon 
			icon="simple-icons:duckduckgo"
			class="w-full h-full group-hover:brightness-115"
			color="#6b6b75"
		/>
	</div>
	<input
		bind:value={searchInput}
		on:keydown={handleSearch}
		on:focus={() => isFocused = true}
		on:blur={() => isFocused = false}
		placeholder="Search anything..."
		class="p-5 px-0 flex-1 bg-transparent text-white text-xl placeholder-gray-400 outline-none"
	/>
</div>

<style>
	.focused {
		background-color: #2c2c3b;
	}
</style>
