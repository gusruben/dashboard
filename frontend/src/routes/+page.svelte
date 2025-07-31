<script lang="ts">
	import WebShortcut from "$lib/components/WebShortcut.svelte";
    import CssFilterConverter from "css-filter-converter";

    // color web shortcuts properly
    const webShortCutFilter = CssFilterConverter.hexToFilter("#6B6B75")

</script>

<div class="min-h-screen bg-gray-950 p-8 flex items-center justify-center">
	<div class="grid grid-cols-10 grid-rows-6 gap-4 w-full max-w-4xl aspect-[5/3]">
		<!-- clock/weather, github/hackatime graph, weighted grants, and airtable stats -->
        <div class="bg-primary-500 rounded-3xl col-span-4 row-span-5"></div>

        <!-- quick links -->
        <WebShortcut src="/freedom.svg" link="https://example.com"/>
		<WebShortcut src="/airtable.svg" link="https://example.com"/>
		<WebShortcut src="/basecamp.svg" link="https://example.com"/>
		
        <!-- bus info OR misc widgets -->
        <div class="bg-gray-900 rounded-3xl col-span-3 row-span-6"></div>
		
        <!-- hackatime stats + ai prompt -->
        <div class="bg-gray-900 rounded-3xl col-span-3 row-span-2"></div>
        <div class="bg-gray-900 rounded-3xl col-span-3 row-span-2"></div>
		
        <!-- web search -->
		<div class="bg-gray-900 rounded-3xl col-span-7 row-span-1"></div>
	</div>
</div>
