<style>
    .weighted-grants::before {
        content: "";
        position: absolute;
        left: 0;
        right: 0;
        top: -4rem;
        bottom: 0;
        background: var(--color-gray-900);
        border-radius: inherit;
        z-index: -1;
    }
    .weighted-grants::after {
        content: "";
        position: absolute;
        left: 100%;
        top: -1rem;
        width: 2.25rem;
        height: 2.25rem;
        z-index: 2;
        border-top-left-radius: 100%;
        box-shadow: -1em -1em 0 1em var(--color-gray-900);
        z-index: -1;
    }
</style>

<div class="col-span-4 row-span-1 flex flex-row gap-4">
    <div class="flex-1 bg-gray-900 rounded-3xl relative weighted-grants"></div>
    <div class="flex-1 bg-gray-900 rounded-3xl"></div>
</div>
