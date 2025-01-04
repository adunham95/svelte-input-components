<script>
	import CodeBlock from '$lib/Components/CodeBlock.svelte';
	import RadioBoxList from '$lib/Components/RadioBoxList.svelte';
</script>

<RadioBoxList
	label="Radio Box List"
	id="radioBoxList"
	groupName="radioBoxList"
	options={[
		{ id: '1', title: 'Option A' },
		{ id: '2', title: 'Option B', checked: true },
		{ id: '3', title: 'Option C', subtitle: 'Subtitle C' }
	]}
/>

<CodeBlock
	code={`
<RadioBoxList
    label="Radio Box List"
    id="radioBoxList"
    groupName="radioBoxList"
    options={[
        { id: '1', title: 'Option A' },
        { id: '2', title: 'Option B', checked: true },
        { id: '3', title: 'Option C', subtitle: 'Subtitle C' }
    ]}
/>
`}
/>
