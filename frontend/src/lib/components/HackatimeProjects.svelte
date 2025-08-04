<script>
	import Icon from "@iconify/svelte";
</script>

<div class="col-span-3 row-span-2 flex flex-col rounded-3xl bg-gray-900">
	<div
		class="hackatime-project flex w-full flex-1 flex-row items-center justify-between gap-2 overflow-hidden rounded-t-3xl p-5"
	>
		<div class="flex min-w-0 flex-1 flex-col">
			<p class="text-sm leading-none text-gray-200">Past 24 Hours</p>
			<p class="truncate text-white">personal-dashboard</p>
		</div>
		<p class="flex-shrink-0 text-3xl text-white">35h</p>
		<Icon icon="simple-icons:typescript" color="#373745" class="lang-icon" />
	</div>
	<hr class="text-gray-500" />
	<div
		class="hackatime-project flex w-full flex-1 flex-row items-center justify-between gap-2 overflow-hidden rounded-b-3xl p-5"
	>
		<div class="flex min-w-0 flex-1 flex-col">
			<p class="text-sm leading-none text-gray-200">Past 7 Days</p>
			<p class="truncate text-white">daydream</p>
		</div>
		<p class="flex-shrink-0 text-3xl text-white">35h</p>
		<Icon icon="simple-icons:svelte" color="#373745" class="lang-icon" />
	</div>

	<!-- <div class="flex-1 flex flex-col justify-center">
        <div class="text-gray-400 text-sm mb-2">Past 24 Hours</div>
        <div class="flex justify-between items-center">
            <div class="text-white text-xl font-medium">personal-dashboard</div>
            <div class="text-white text-4xl font-light">4h</div>
        </div>
    </div>
    
    <div class="border-t border-gray-700 my-4"></div>
    
    <div class="flex-1 flex flex-col justify-center">
        <div class="text-gray-400 text-sm mb-2">Past 7 Days</div>
        <div class="flex justify-between items-center">
            <div class="text-white text-xl font-medium">daydream</div>
            <div class="flex items-center gap-2">
                <div class="text-white text-4xl font-light">35h</div>
                <div class="text-green-500 text-lg">▲</div>
            </div>
        </div>
    </div> -->
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
