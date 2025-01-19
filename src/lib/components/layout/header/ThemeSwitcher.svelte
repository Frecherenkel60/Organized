<script lang="ts">
	import { onMount } from 'svelte';

	const injectedTheme = `
        <\u{73}cript nonce="%sveltekit.nonce%">
            document.documentElement.classList.toggle(
                'dark',
                localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)
            );
        <\/script>
    `;

	const getSelectedTheme = () => {
		if (typeof localStorage !== 'undefined' && localStorage.getItem('theme')) {
			return localStorage.getItem('theme');
		}
		if (window.matchMedia('(prefers-color-scheme: dark)').matches) {
			return 'dark';
		}
		return 'light';
	};

	const handleToggleClick = () => {
		const element = document.documentElement;
		const isDarkModeEnabled = element.classList.toggle('dark');
		localStorage.setItem('theme', isDarkModeEnabled ? 'dark' : 'light');
	};

	onMount(() => {
		const selectedTheme = getSelectedTheme() || 'light';

		if (selectedTheme === 'light') {
			document.documentElement.classList.remove('dark');
		} else {
			document.documentElement.classList.add('dark');
		}

		window.localStorage.setItem('theme', selectedTheme);

		const elemsLightswitch = document.querySelectorAll('[data-lightswitch]');
		elemsLightswitch.forEach((ls) => ls.addEventListener('click', handleToggleClick));
	});
</script>

<svelte:head>
	{@html injectedTheme}
</svelte:head>
