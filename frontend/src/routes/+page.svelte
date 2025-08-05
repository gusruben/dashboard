<script lang="ts">
	import { HackatimeProjects, WebShortcut, AIChat, WebSearch, Welcome, CommitGraph } from "$lib";
</script>

<div class="flex min-h-screen items-center justify-center bg-gray-950 p-8">
	<div class="grid aspect-[5/3] w-full max-w-4xl grid-cols-10 grid-rows-6 gap-4">
		<!-- clock/weather, github/hackatime graph, weighted grants, and airtable stats -->
		<div class="col-span-4 row-span-4 rounded-3xl flex flex-col gap-4">
			<Welcome />
			<CommitGraph />
		</div>

		<!-- quick links -->
		<WebShortcut icon="ph:butterfly" link="https://example.com" />
		<WebShortcut icon="simple-icons:airtable" link="https://example.com" />
		<WebShortcut icon="simple-icons:basecamp" link="https://example.com" />

		<!-- bus info OR misc widgets -->
		<div class="col-span-3 row-span-6 rounded-3xl bg-gray-900"></div>

		<!-- hackatime projects -->
		<HackatimeProjects />

		<!-- ai prompt -->
		<AIChat />

		<!-- hackatime stats -->
		<div class="col-span-4 row-span-1 bg-gray-900 rounded-3xl"></div>

		<!-- web search -->
		<WebSearch />
	</div>
</div>
