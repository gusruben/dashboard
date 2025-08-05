<script lang="ts">
	import HackatimeProjects from "$lib/components/HackatimeProjects.svelte";
	import WebShortcut from "$lib/components/WebShortcut.svelte";
	import AIChat from "$lib/components/AIChat.svelte";
</script>

<div class="flex min-h-screen items-center justify-center bg-gray-950 p-8">
	<div class="grid aspect-[5/3] w-full max-w-4xl grid-cols-10 grid-rows-6 gap-4">
		<!-- clock/weather, github/hackatime graph, weighted grants, and airtable stats -->
		<div class="col-span-4 row-span-5 rounded-3xl bg-primary-500"></div>

		<!-- quick links -->
		<WebShortcut icon="ph:butterfly" link="https://example.com" />
		<WebShortcut icon="simple-icons:airtable" link="https://example.com" />
		<WebShortcut icon="simple-icons:basecamp" link="https://example.com" />

		<!-- bus info OR misc widgets -->
		<div class="col-span-3 row-span-6 rounded-3xl bg-gray-900"></div>

		<!-- hackatime stats -->
		<HackatimeProjects />
		<!-- ai prompt -->
		<AIChat />

		<!-- web search -->
		<div class="col-span-7 row-span-1 rounded-3xl bg-gray-900"></div>
	</div>
</div>
