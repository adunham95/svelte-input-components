<script>
	import CodeBlock from '$lib/Components/CodeBlock.svelte';
	import Select from '$lib/Components/Select.svelte';
</script>

<Select
	id="select"
	label="Select"
	options={[
		{ id: 'select', label: 'Select an Option', selected: true },
		{ id: '1', label: 'Option 1' },
		{ id: '2', label: 'Option 2' }
	]}
/>

<CodeBlock
	code={`
<Select
	id="select"
	label="Select"
	options={[
		{ id: 'select', label: 'Select an Option', selected: true },
		{ id: '1', label: 'Option 1' },
		{ id: '2', label: 'Option 2' }
	]}
/>
`}
/>
