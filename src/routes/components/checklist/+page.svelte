<script>
	import Checklist from '$lib/Components/Checklist.svelte';
	import CodeBlock from '$lib/Components/CodeBlock.svelte';
</script>

<Checklist
	options={[
		{ id: '1', title: 'Option 1' },
		{ id: '2', title: 'Option 2' }
	]}
/>

<CodeBlock
	code={`
<Checklist
	options={[
		{ id: '1', title: 'Option 1' },
		{ id: '2', title: 'Option 2' }
	]}
/>`}
/>
