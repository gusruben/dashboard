<script lang="ts">
	import HackatimeProjects from "$lib/components/HackatimeProjects.svelte";
    import WebShortcut from "$lib/components/WebShortcut.svelte";
</script>

<div class="min-h-screen bg-gray-950 p-8 flex items-center justify-center">
	<div class="grid grid-cols-10 grid-rows-6 gap-4 w-full max-w-4xl aspect-[5/3]">
		<!-- clock/weather, github/hackatime graph, weighted grants, and airtable stats -->
        <div class="bg-primary-500 rounded-3xl col-span-4 row-span-5"></div>

        <!-- quick links -->
        <WebShortcut icon="ph:butterfly" link="https://example.com"/>
        <WebShortcut icon="simple-icons:airtable" link="https://example.com"/>
        <WebShortcut icon="simple-icons:basecamp" link="https://example.com"/>
		
        <!-- bus info OR misc widgets -->
        <div class="bg-gray-900 rounded-3xl col-span-3 row-span-6"></div>
		
        <!-- hackatime stats + ai prompt -->
        <HackatimeProjects />
        <div class="bg-gray-900 rounded-3xl col-span-3 row-span-2"></div>
		
        <!-- web search -->
		<div class="bg-gray-900 rounded-3xl col-span-7 row-span-1"></div>
	</div>
</div>
