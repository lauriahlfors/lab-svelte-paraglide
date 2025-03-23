<script lang="ts">
	import { m } from '../paraglide/messages';
	import { setLocale } from '../paraglide/runtime';
</script>

<div class="flex w-full flex-col items-center justify-center gap-4 py-24">
	<div>
		<button class="rounded-lg bg-neutral-200 px-3 py-1" onclick={() => setLocale('en')}>en</button>
		<button class="rounded-lg bg-neutral-200 px-3 py-1" onclick={() => setLocale('fi')}>fi</button>
	</div>

	<h1 class="text-2xl text-neutral-900">{m.greeting_message()}</h1>
</div>
