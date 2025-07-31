<script lang="ts">
    import { iconFilter } from "$lib/colors"

    export let src: string;
    export let link: string;
</script>

<style>
    img {
        filter: var(--filter);
    }

    img:hover {
        filter: var(--filter) brightness(110%);
    }
</style>

<a class="bg-gray-900 hover:bg-gray-800 transition-colors duration-50 rounded-3xl col-span-1 row-span-1 flex align-center justify-center" href={link}>
    <img src={src} alt="" class="p-5" style="--filter: {iconFilter}">
</a>
