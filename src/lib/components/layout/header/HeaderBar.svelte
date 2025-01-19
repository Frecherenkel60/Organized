<script lang="ts">
	import { Avatar } from '@skeletonlabs/skeleton-svelte';
	import Settings from 'lucide-svelte/icons/settings';
	import ChevronDown from 'lucide-svelte/icons/chevron-down';
	import Inbox from 'lucide-svelte/icons/inbox';
	import Lightbulb from 'lucide-svelte/icons/lightbulb';

	const name = 'Tom Cook';
</script>

<div class="flex flex-row">
	<div class="flex-1"></div>
	<div class="ml-auto flex flex-row items-center gap-4 p-2">
		<div class="relative inline-block">
			<button data-lightswitch type="button" class="btn-icon btn-icon-lg preset-filled">
				<Lightbulb class="h-12 w-12" />
			</button>
		</div>
		<div class="relative inline-block">
			<span class="badge-icon absolute -right-1 -top-1 z-10 preset-filled-primary-900-100">2</span>
			<button type="button" class="btn-icon btn-icon-lg preset-filled">
				<Inbox class="h-12 w-12" />
			</button>
		</div>
		<div class="relative inline-block">
			<button type="button" class="btn-icon btn-icon-lg preset-filled">
				<Settings class="h-12 w-12" />
			</button>
		</div>
	</div>
	<div class="mr-6 flex flex-row items-center gap-4 p-2">
		<span class="vr border-l-2 opacity-20"></span>
		<Avatar {name} size="w-10 h-10" />
		<p class=" font-semibold text-surface-50-950">Tom Cook</p>
		<ChevronDown class="text-surface-100-900" />
	</div>
</div>
