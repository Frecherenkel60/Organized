<script lang="ts">
	import House from 'lucide-svelte/icons/house';
	import Calendar from 'lucide-svelte/icons/calendar';
	import ListCheck from 'lucide-svelte/icons/list-check';
	import SidebarItem from './SidebarItem.svelte';
	import Timer from 'lucide-svelte/icons/timer';

	const topNavigationItems = [
		{
			icon: House,
			link: '/',
			title: 'Homepage'
		},
		{
			icon: Calendar,
			link: '/calendar',
			title: 'Calendar'
		},
		{
			icon: ListCheck,
			link: '/tasks',
			title: 'Tasks'
		},
		{
			icon: Timer,
			link: '/tracking',
			title: 'Tracking'
		}
	];
</script>

<div class="mx-auto flex h-full flex-col py-4">
	<div class="flex w-full flex-1 flex-col gap-3 p-2">
		{#each topNavigationItems as item}
			<SidebarItem icon={item.icon} link={item.link} title={item.title} />
		{/each}
	</div>
	<!-- BOTTOM SECTION OF MAIN SECTION-->
	<div class="mt-auto flex flex-col gap-2 p-2">
		<!-- Currently empty, but may be used later -->
	</div>
</div>
