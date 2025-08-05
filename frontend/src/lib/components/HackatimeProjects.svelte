<script lang="ts">
	import Icon from "@iconify/svelte";

	interface Project {
		name: string;
		time: string;
		lang: string;
		link: string;
	}

	const projectDay: Project = {
		name: "personal-dashboard",
		time: "35h",
		lang: "typescript",
		link: "https://example.com",
	};

	const projectWeek: Project = {
		name: "daydream",
		time: "35h",
		lang: "svelte",
		link: "https://example.com",
	}
</script>

{#snippet projectItem(project: Project, timeframe: string)}
	<a
		href={project.link}
		target="_blank"
		class="hackatime-project flex w-full flex-1 flex-row items-center justify-between gap-4 overflow-hidden p-5 hover:bg-gray-850 group transition-all duration-50"
	>
		<div class="flex min-w-0 flex-1 flex-col">
			<p class="text-sm leading-none text-gray-200">{timeframe}</p>
			<div class="project-name-container after:bg-linear-to-l after:from-gray-900 group-hover:after:from-gray-850 after:transition after:duration-50">
				<p class="project-name text-white">{project.name}</p>
			</div>
		</div>
		<p class="flex-shrink-0 text-3xl text-white">{project.time}</p>
		<Icon icon="simple-icons:{project.lang}" color="#373745" class="lang-icon group-hover:brightness-110 transition-all duration-50" />
	</a>
{/snippet}

<div class="col-span-3 row-span-2 flex flex-col rounded-3xl bg-gray-900 overflow-hidden">
	{@render projectItem(projectDay, "Past 24 hours")}
	<hr class="text-gray-500" />
	{@render projectItem(projectWeek, "Past 7 days")}
</div>

<style>
	.hackatime-project {
		position: relative;
		z-index: 0;
	}
	
	.project-name-container {
		position: relative;
		overflow: hidden;
		width: 100%;
	}
	
	.project-name {
		white-space: nowrap;
		overflow: hidden;
		position: relative;
	}
	
	.project-name-container::after {
		content: '';
		position: absolute;
		top: 0;
		right: 0;
		width: 2rem;
		height: 100%;
		pointer-events: none;
	}
	
	:global(.lang-icon) {
		position: absolute;
		bottom: -1.5rem;
		right: -0.5rem;
		width: 6rem;
		height: 6rem;
		z-index: -1;
	}
</style>
