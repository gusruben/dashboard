<script lang="ts">
	import Icon from "@iconify/svelte";
</script>

<div class="col-span-3 row-span-2 relative rounded-3xl bg-gray-900 p-6 hover:bg-gray-850 [:has(textarea:focus)]:bg-gray-850 transition-all duration-50 group">
	<textarea 
		placeholder="Start typing..."
		class="w-full h-full bg-transparent text-white placeholder-gray-400 outline-none resize-none text-xl align-top"
	></textarea>
	<Icon 
		icon="fluent:sparkle-28-regular" 
		class="absolute bottom-6 right-6 w-10 h-10 text-gray-400 pointer-events-none group-[:has(textarea:focus)]:opacity-0 transition-opacity duration-100"
	/>
</div>
