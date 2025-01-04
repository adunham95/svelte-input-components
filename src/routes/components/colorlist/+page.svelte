<script>
	import CodeBlock from '$lib/Components/CodeBlock.svelte';
	import ColorInput from '$lib/Components/ColorInput.svelte';
</script>

<ColorInput
	id="color"
	label="Select A Color"
	groupName="colors"
	colors={[
		{ hex: '#FF5733', name: 'Sunset Orange' },
		{ hex: '#33FF57', name: 'Lime Green' },
		{ hex: '#3357FF', name: 'Royal Blue' },
		{ hex: '#F4C2C2', name: 'Baby Pink' },
		{ hex: '#FFD700', name: 'Golden Yellow' },
		{ hex: '#800080', name: 'Deep Purple' },
		{ hex: '#00FFFF', name: 'Cyan' },
		{ hex: '#FFA500', name: 'Orange' },
		{ hex: '#008080', name: 'Teal' },
		{ hex: '#DC143C', name: 'Crimson' }
	]}
/>

<CodeBlock
	code={`
<ColorInput
	id="color"
	label="Select A Color"
	groupName="colors"
	colors={[
		{ hex: '#FF5733', name: 'Sunset Orange' },
		{ hex: '#33FF57', name: 'Lime Green' },
		{ hex: '#3357FF', name: 'Royal Blue' },
	]}
/>	 

`}
/>
