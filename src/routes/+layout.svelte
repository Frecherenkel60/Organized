<script lang="ts">
	import HeaderBar from '$lib/components/layout/header/HeaderBar.svelte';
	import ThemeSwitcher from '$lib/components/layout/header/ThemeSwitcher.svelte';
	import SidebarPane from '$lib/components/layout/sidebar/SidebarPane.svelte';
	import '../app.css';
	let { children } = $props();
</script>

<div data-element="wrapper" class="wrapper">
	<div class="context">
		<ThemeSwitcher />
	</div>
	<div class="app">
		<div class="grid grid-cols-12 bg-surface-950-50">
			<!-- Sidebar -->
			<aside data-element="sidebar" class="sticky top-0 col-span-4 h-screen">
				<SidebarPane />
			</aside>
			<!-- Grid Column -->
			<div class="col-span-8 grid h-screen grid-rows-[auto_1fr]">
				<!-- Navbar -->
				<nav data-element="navbar" class="border-b-2 border-gray-200">
					<HeaderBar />
				</nav>
				<!-- Main -->
				<main data-element="wrapper" class="space-y-4 p-4">
					{@render children()}
				</main>
			</div>
		</div>
		<!-- Footer -->
		<footer class="bg-blue-500 p-4">(footer)</footer>
	</div>
</div>
