<script lang="ts">
	import Label, { type LabelProps } from '$lib/Components/Label.svelte';

	interface Props extends LabelProps {
		class?: string;
		groupName: string;
		colors?: { hex: string; name?: string; checked?: boolean }[];
	}

	let { class: className, label, id, groupName, hideLabel = false, colors = [] }: Props = $props();
</script>

<div class={className}>
	<Label {id} {label} {hideLabel} />
	<div class="flex justify-start">
		{#each colors as color}
			<label
				aria-label={color.name || color.hex}
				style={`color: ${color.hex}`}
				class="relative -m-0.5 mb-1 mr-1 flex cursor-pointer items-center justify-center rounded-full p-0.5 focus:outline-none"
			>
				<input
					type="radio"
					name={groupName}
					value={color.hex}
					checked={color.checked}
					class="peer sr-only"
				/>
				<span
					aria-hidden="true"
					class="h-8 w-8 rounded-full border-2 border-gray-300 bg-current peer-[:checked]:border-gray-900"
				></span>
			</label>
		{/each}
	</div>
</div>
