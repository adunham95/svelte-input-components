<!-- @migration-task Error while migrating Svelte code: $$props is used together with named props in a way that cannot be automatically migrated. -->
<script lang="ts">
	import Label from '$lib/Components/Label.svelte';

	export let label: string;
	export let id: string;
	export let placeholder: string = '';
	export let type: string = 'text';
	export let value: any = '';
	export let name: string | undefined = undefined;
	export let cols: number = 3;
	export let inputClass: string = '';
	export let showLabel = false;
	export let disabled = false;

	export let required = false;

	export let inputRef = null;
</script>

<div class="mt-2 {$$props.class}">
	<Label {label} {id} {showLabel} />
	<textarea
		class={`bg-theme-surface text-theme-content placeholder:text-theme-secondary-content focus:ring-theme-brand block w-full rounded-md border-0 p-1.5 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset sm:text-sm sm:leading-6 ${inputClass}`}
		{id}
		{placeholder}
		{required}
		{cols}
		{disabled}
		name={name || id}
		bind:value
		bind:this={inputRef}
	>
	</textarea>
</div>
