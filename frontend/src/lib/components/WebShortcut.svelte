<script lang="ts">
	import Icon from "@iconify/svelte";

	export let icon: string;
	export let link: string;
</script>

<a
	class="col-span-1 row-span-1 flex items-center justify-center rounded-3xl bg-gray-900 transition-colors duration-50 hover:bg-gray-800"
	href={link}
>
	<Icon {icon} width="100%" height="100%" color="#6B6B75" class="p-5 hover:brightness-110" />
</a>
