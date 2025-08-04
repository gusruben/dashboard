<script>
	import Icon from "@iconify/svelte";

	const projectDay = {
		name: "personal-dashboard",
		time: "35h",
		lang: "typescript",
	};

	const projectWeek = {
		name: "daydream",
		time: "35h",
		lang: "svelte",
	}
</script>

<div class="col-span-3 row-span-2 flex flex-col rounded-3xl bg-gray-900">
	<div
		class="hackatime-project flex w-full flex-1 flex-row items-center justify-between gap-2 overflow-hidden rounded-t-3xl p-5"
	>
		<div class="flex min-w-0 flex-1 flex-col">
			<p class="text-sm leading-none text-gray-200">Past 24 hours</p>
			<p class="truncate text-white">{projectDay.name}</p>
		</div>
		<p class="flex-shrink-0 text-3xl text-white">{projectDay.time}</p>
		<Icon icon="simple-icons:{projectDay.lang}" color="#373745" class="lang-icon" />
	</div>
	<hr class="text-gray-500" />
	<div
		class="hackatime-project flex w-full flex-1 flex-row items-center justify-between gap-2 overflow-hidden rounded-b-3xl p-5"
	>
		<div class="flex min-w-0 flex-1 flex-col">
			<p class="text-sm leading-none text-gray-200">Past 7 days</p>
			<p class="truncate text-white">{projectWeek.name}</p>
		</div>
		<p class="flex-shrink-0 text-3xl text-white">{projectWeek.time}</p>
		<Icon icon="simple-icons:{projectWeek.lang}" color="#373745" class="lang-icon" />
	</div>
</div>

<style>
	.hackatime-project {
		position: relative;
		z-index: 0;
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
