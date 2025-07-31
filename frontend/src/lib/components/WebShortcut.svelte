<script lang="ts">
    import Icon from "@iconify/svelte"

    export let icon: string;
    export let link: string;
</script>

<a class="bg-gray-900 hover:bg-gray-800 transition-colors duration-50 rounded-3xl col-span-1 row-span-1 flex items-center justify-center" href={link}>
    <Icon {icon} width="100%" height="100%" color="#6B6B75" class="p-5 hover:brightness-110" />
</a>
