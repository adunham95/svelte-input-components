<!-- @migration-task Error while migrating Svelte code: $$props is used together with named props in a way that cannot be automatically migrated. -->
<script lang="ts">
	import Label, { type LabelProps } from '$lib/Components/Label.svelte';

	interface RadioBoxProps extends LabelProps {
		groupName: string;
		class?: string;
		options: { id: string; title: string; value?: string; checked?: boolean }[];
	}

	const { label, id, groupName, options = [], class: className = '' }: RadioBoxProps = $props();
</script>

<fieldset class={className}>
	{#if label}
		<Label {label} {id} />
	{/if}

	<div class="grid-template-auto mt-2 grid gap-x-4 gap-y-6">
		{#each options as radioElement}
			<label
				class="bg-theme-surface has-[:checked]:border-theme-brand has-[:checked]:ring-theme-brand has-[:checked]:bg-theme-brand-bg relative flex cursor-pointer rounded-lg border p-4 shadow-sm focus:outline-none has-[:checked]:ring-1"
			>
				<input
					type="radio"
					id={radioElement.id}
					name={groupName}
					value={radioElement?.value || radioElement.id}
					checked={radioElement.checked}
					class="peer sr-only"
					aria-labelledby="project-type-0-label"
					aria-describedby="project-type-0-description-0 project-type-0-description-1"
				/>
				<span class="text-theme-brand-content flex flex-1">
					<span id="project-type-0-label" class="block text-sm font-medium">
						{radioElement.title}
					</span>
				</span>

				<svg
					class="peer-[:checked]:text-theme-brand-icon h-5 w-5 text-transparent"
					viewBox="0 0 20 20"
					fill="currentColor"
					aria-hidden="true"
				>
					<path
						fill-rule="evenodd"
						d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
						clip-rule="evenodd"
					/>
				</svg>

				<span
					class="peer-[:checked]:border-theme-brand pointer-events-none absolute -inset-px rounded-lg border-2 border-transparent"
					aria-hidden="true"
				></span>
			</label>
		{/each}
	</div>
</fieldset>
