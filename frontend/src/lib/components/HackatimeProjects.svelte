<style>
.hackatime-project {
    position: relative;
    z-index: 0;
}
.hackatime-project::after {
    content: "";
    position: absolute;
    bottom: -0.5rem;
    right: 0.25rem;
    width: 5rem;
    height: 5rem;
    background-image: var(--lang-img);
    background-size: cover;
    z-index: -1;
}
.hackatime-increase::after {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
}
</style>

<div class="bg-gray-900 rounded-3xl col-span-3 row-span-2 flex flex-col">
    <div
        class="hackatime-project w-full flex-1 p-5 flex flex-row items-center justify-between gap-2 overflow-hidden rounded-t-3xl"
        style="--lang-img: url(/typescript.svg)"
    >
        <div class="flex flex-col min-w-0 flex-1">
            <p class="text-gray-200 text-sm leading-none">Past 24 Hours</p>
            <p class="text-white truncate">personal-dashboard</p>
        </div>
        <p class="text-white text-3xl flex-shrink-0">35h</p>
    </div>
    <hr class="text-gray-500">
        <div class="hackatime-project w-full flex-1 p-5 flex flex-row items-center justify-between gap-2 overflow-hidden rounded-b-3xl"
        style="--lang-img: url(/svelte.svg)"
    >
        <div class="flex flex-col min-w-0 flex-1">
            <p class="text-gray-200 text-sm leading-none">Past 7 Days</p>
            <p class="text-white truncate">daydream</p>
        </div>
        <p class="text-white text-3xl flex-shrink-0 hackatime-increase">35h</p>
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
