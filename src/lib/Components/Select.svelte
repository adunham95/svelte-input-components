<!-- @migration-task Error while migrating Svelte code: $$props is used together with named props in a way that cannot be automatically migrated. -->
<script lang="ts">
	import Label, { type LabelProps } from '$lib/Components/Label.svelte';

	interface SelectProps extends LabelProps {
		class?: string;
		name?: string;
		value?: string | null;
		options: { id: string; label?: string; selected?: boolean }[];
		hideLabel?: boolean;
		required?: boolean;
	}

	let {
		class: className,
		label,
		id,
		hideLabel,
		required,
		name,
		value = $bindable(),
		options
	}: SelectProps = $props();
</script>

<div class={className}>
	<Label {label} {id} {hideLabel} />
	<select
		{required}
		name={name || id}
		bind:value
		class="text-theme-content placeholder:text-theme-secondary-content focus:ring-theme-brand block w-full rounded-md border-0 bg-white px-1.5 py-1.5 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset sm:text-[1.2rem] sm:leading-6"
	>
		{#each options as option}
			<option value={option.id} selected={option.selected || false}
				>{option?.label || option.id}</option
			>
		{/each}
	</select>
</div>
