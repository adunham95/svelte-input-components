<script lang="ts">
	import Label from '$lib/Components/Label.svelte';

	export let label: string;
	export let id: string;
	export let placeholder: string = '';
	export let value: any = '';
	export let name: string | undefined = undefined;
	export let error: string | undefined = undefined;

	export let required = false;

	export let inputRef = null;
</script>

<div class={$$props.class}>
	<Label {label} {id} />
	<input
		type="date"
		class="bg-theme-surface text-theme-content placeholder:text-theme-secondary-content focus:ring-theme-brand block w-full rounded-md border-0 p-1.5 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset sm:text-sm sm:leading-6"
		{id}
		{placeholder}
		{required}
		name={name || id}
		bind:value
		bind:this={inputRef}
	/>
	{#if error}
		<p class="mt-2 text-sm text-red-600">{error}</p>
	{/if}
</div>
