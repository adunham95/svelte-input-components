<script lang="ts">
	import Label, { type LabelProps } from '$lib/Components/Label.svelte';

	export type TextInputTypes =
		| 'date'
		| 'datetime-local'
		| 'email'
		| 'password'
		| 'search'
		| 'tel'
		| 'text'
		| 'time'
		| 'url';
	interface TextInputProps extends LabelProps {
		name?: string;
		class?: string;
		placeholder?: string;
		type?: TextInputTypes;
		value?: string | null;
		error?: string;
		disabled?: boolean;
		required?: boolean;
	}
	let {
		id,
		label,
		name,
		hideLabel,
		class: className,
		placeholder,
		type = 'text',
		value = $bindable(),
		error,
		disabled = false,
		required = false
	}: TextInputProps = $props();
</script>

<div class={className}>
	<Label {label} {id} {hideLabel} />
	<input
		class="bg-theme-surface text-theme-content placeholder:text-theme-secondary-content focus:ring-theme-brand block w-full rounded-md border-0 p-1.5 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset sm:text-sm sm:leading-6"
		{id}
		{placeholder}
		{required}
		{disabled}
		{type}
		name={name || id}
		bind:value
	/>
	{#if error}
		<p class="mt-2 text-sm text-red-600">{error}</p>
	{/if}
</div>
