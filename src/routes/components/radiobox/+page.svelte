<script>
	import CodeBlock from '$lib/Components/CodeBlock.svelte';
	import RadioBox from '$lib/Components/RadioBox.svelte';
</script>

<RadioBox
	label="Radio Box"
	id="radioBox"
	groupName="options"
	options={[
		{ id: '1', title: 'Option A', value: '1' },
		{ id: '2', title: 'Option B', value: '2' }
	]}
/>

<CodeBlock
	code={`
<RadioBox
    label="Radio Box"
    id="radioBox"
    groupName="options"
    options={[
        { id: '1', title: 'Option A', value: '1' },
        { id: '2', title: 'Option B', value: '2' }
    ]}
/>
`}
></CodeBlock>
