<!-- @migration-task Error while migrating Svelte code: $$props is used together with named props in a way that cannot be automatically migrated. -->
<script lang="ts">
	import Label, { type LabelProps } from '$lib/Components/Label.svelte';

	interface TextAreaProps extends LabelProps {
		class?: string;
		placeholder?: string;
		value?: string | null;
		name?: string;
		cols?: number;
		inputClass?: string;
		disabled?: boolean;
		required?: boolean;
	}

	let {
		value = $bindable(),
		class: className,
		label,
		id,
		placeholder = '',
		name,
		cols = 3,
		inputClass,
		disabled = false,
		required = false,
		hideLabel = false
	}: TextAreaProps = $props();
</script>

<div class="mt-2 {className}">
	<Label {label} {id} {hideLabel} />
	<textarea
		class={`bg-theme-surface text-theme-content placeholder:text-theme-secondary-content focus:ring-theme-brand block w-full rounded-md border-0 p-1.5 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset sm:text-sm sm:leading-6 ${inputClass}`}
		{id}
		{placeholder}
		{required}
		{cols}
		{disabled}
		name={name || id}
		bind:value
	>
	</textarea>
</div>
