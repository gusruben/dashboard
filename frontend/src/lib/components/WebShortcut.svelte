<script lang="ts">
    import CssFilterConverter from "css-filter-converter";

    export let src: string;
    export let link: string;

    // dynamically generate filters to color the icon properly
    // this color is gray-400
    const webShortCutFilter = CssFilterConverter.hexToFilter("#6B6B75", { sheen: true })
</script>

<a class="bg-gray-900 hover:bg-gray-800 transition-colors duration-50 rounded-3xl col-span-1 row-span-1 flex align-center justify-center" href={link}>
    <img src={src} alt="" class="p-5" style="filter: {webShortCutFilter.color}">
</a>
