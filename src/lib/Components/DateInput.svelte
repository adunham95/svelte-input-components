<script lang="ts">
	import Label, { type LabelProps } from '$lib/Components/Label.svelte';

	interface DateInputProps extends LabelProps {
		placeholder?: string;
		value?: string;
		name?: string;
		error?: string;
		required?: boolean;
	}

	let {
		class: className,
		label,
		id,
		placeholder,
		required = false,
		name,
		value = $bindable(),
		error,
		hideLabel
	}: DateInputProps = $props();
</script>

<div class={className}>
	<Label {label} {id} {hideLabel} />
	<input
		type="date"
		class="text-theme-content placeholder:text-theme-secondary-content focus:ring-theme-brand block w-full rounded-md border-0 p-1.5 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset sm:text-sm sm:leading-6"
		{id}
		{placeholder}
		{required}
		name={name || id}
		bind:value
	/>
	{#if error}
		<p class="mt-2 text-sm text-red-600">{error}</p>
	{/if}
</div>
