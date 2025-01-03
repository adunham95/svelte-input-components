<!-- @migration-task Error while migrating Svelte code: $$props is used together with named props in a way that cannot be automatically migrated. -->
<script lang="ts">
	import Label from '$lib/Components/Label.svelte';

	export let label: string | undefined = undefined;
	export let id: string;
	export let value: any = '';
	export let name: string | undefined = undefined;
	export let options: { id: string; label?: string; selected?: boolean }[] = [];
	export let showLabel = true;

	export let required = false;
</script>

<div class={$$props.class}>
	{#if label}
		<Label {label} {id} {showLabel} />
	{/if}
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
