<script lang="ts">
	import { m } from '../paraglide/messages';
	import { setLocale } from '../paraglide/runtime';

	let dogAmount = $state(0);
</script>

<div class="flex w-full flex-col items-center justify-center gap-4 py-24">
	<!-- Locale switcher -->
	<div>
		<button
			class="rounded-xl border border-neutral-200 bg-neutral-100 px-3 py-2 font-sans shadow-xl"
			onclick={() => setLocale('en')}>en</button
		>
		<button
			class="rounded-xl border border-neutral-200 bg-neutral-100 px-3 py-2 font-sans shadow-xl"
			onclick={() => setLocale('fi')}>fi</button
		>
	</div>

	<!-- Add or remove dogs -->
	<div>
		<button
			class="rounded-xl border border-neutral-200 bg-neutral-100 px-3 py-2 font-sans shadow-xl"
			onclick={() => dogAmount++}
		>
			{m.dogButtonAdd()}
		</button>
		<button
			class="rounded-xl border border-neutral-200 bg-neutral-100 px-3 py-2 font-sans shadow-xl"
			onclick={() => dogAmount--}
		>
			{m.dogButtonRemove()}
		</button>
	</div>

	<!-- Dog count -->
	<div>
		<span>{m.dogsAmount({ count: dogAmount })}</span>
	</div>

	<div class="my-12 flex flex-col items-center justify-center gap-4">
		<!-- Greeting -->
		<h1 class="font-sans text-5xl font-medium tracking-tight text-neutral-900">
			{m.helloWorld({ user: 'Lauri' })}
		</h1>

		<!-- Dog message -->
		<h2 class="font-sans text-2xl text-neutral-900">
			{#if dogAmount < 1}
				{m.dogsZero()}
			{:else}
				{m.dogs({ count: dogAmount })}
			{/if}
		</h2>
	</div>
</div>
