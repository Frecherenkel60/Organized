<script lang="ts">
	import SidebarHeader from './SidebarHeader.svelte';
	import NavigationLeftSplit from './NavigationLeftSplit.svelte';
	import NavigationRightSplit from './NavigationRightSplit.svelte';
</script>

<div class="flex h-screen flex-col rounded-sm border-r-2 border-gray-200">
	<div class="h-22">
		<SidebarHeader />
	</div>
	<div class="grid h-full grid-cols-5 border-t-2">
		<div class="col-span-2 border-r-2 border-gray-200">
			<NavigationLeftSplit />
		</div>
		<div class="col-span-3">
			<NavigationRightSplit />
		</div>
	</div>
</div>
