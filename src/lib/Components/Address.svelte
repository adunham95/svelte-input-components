<script lang="ts">
	import Select from '$lib/Components/Select.svelte';
	import TextInput from '$lib/Components/TextInput.svelte';

	interface AddressProps {
		class?: string;
	}

	let { class: className = '' }: AddressProps = $props();
</script>

<div class={`grid grid-cols-3 gap-2 ${className}`}>
	<TextInput id="location-name" label="Address Name" class="col-span-3" />
	<TextInput id="street" label="Street" class="col-span-3" />
	<TextInput id="street2" label="Street 2" class="col-span-3" />
	<TextInput id="city" label="City" class="col-span-1" />
	<Select
		id="state"
		label="State"
		class="col-span-1"
		options={[{ id: 'TN', label: 'Tennessee' }]}
	/>
	<TextInput id="zip" label="Zip/Postal Code" class="col-span-1" />
</div>
