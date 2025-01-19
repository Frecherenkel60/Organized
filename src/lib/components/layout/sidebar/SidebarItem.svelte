<script lang="ts">
	import { page } from '$app/state';
	import { type Icon } from 'lucide-svelte';
	import type { Snippet } from 'svelte';

	interface SidebarItemProps {
		icon: typeof Icon;
		link?: string;
		title: string;
		children?: Snippet;
	}

	let { icon: NavigationIcon, link, title, children }: SidebarItemProps = $props();

	const selected = $derived(link && page.url.pathname === link);
</script>

{#if link}
	<a
		type="button"
		class={[
			'btn btn-lg place-content-start rounded-xl',
			selected && 'preset-filled-primary-900-100',
			!selected && 'preset-filled'
		]}
		href={link}
	>
		<span><NavigationIcon /></span>
		<span>{title}</span>
		{@render children?.()}
	</a>
{:else}
	<button type="button" class="btn btn-lg place-content-start rounded-xl preset-filled">
		<span><NavigationIcon /></span>
		<span>{title}</span>
		{@render children?.()}
	</button>
{/if}
