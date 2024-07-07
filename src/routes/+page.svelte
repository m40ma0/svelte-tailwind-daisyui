<script lang="ts">
	import { onMount } from 'svelte';
	import { themes } from '$lib/themes';
	import { fly } from 'svelte/transition';

	let currentTheme = '';

	onMount(() => {
		if (typeof window !== 'undefined') {
			const theme = window.localStorage.getItem('theme');
			if (theme && themes.includes(theme)) {
				document.documentElement.setAttribute('data-theme', theme);
				currentTheme = theme;
			}
		}
	});

	function setTheme(event: Event) {
		const select = event.target as HTMLSelectElement;
		const theme = select.value;
		if (themes.includes(theme)) {
			const one_year = 60 * 60 * 24 * 365;
			window.localStorage.setItem('theme', theme);
			document.cookie = `theme=${theme}; max-age=${one_year}; path=/; SameSite=Strict;`;
			document.documentElement.setAttribute('data-theme', theme);
			currentTheme = theme;
		}
	}
</script>

<div in:fly={{ y: 50, duration: 500, delay: 800 }} out:fly={{ y: 50, duration: 500 }}>

	<div class="mx-auto w-full max-w-xl px-10">
		<select
			data-choose-theme
			class="select select-bordered select-primary mx-auto my-5 w-full max-w-3xl text-xl capitalize"
			on:change={setTheme}
		>
			<option disabled selected>Choose a theme</option>
			{#each themes as theme}
				<option value={theme} class="capitalize">{theme}</option>
			{/each}
		</select>
	</div>
</div>
