<script lang="ts">
	import '../app.css';
	import { page } from '$app/state';
	import { locales, localizeHref } from '../paraglide/runtime';

	let { children } = $props();
</script>

<div style="display:none">
	{#each locales as locale (locale)}
		<a href={localizeHref(page.url.pathname, { locale })}>{locale}</a>
	{/each}
</div>

{@render children()}
