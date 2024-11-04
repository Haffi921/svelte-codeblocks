<script lang="ts">
	import CodeblockArray from '../primatives/Array.svelte';
	import CodeblockObject from '../primatives/Object.svelte';
	import CodeblockLiteral from '../primatives/Literal.svelte';

	interface Props {
		name: string;
		value: unknown;
		strikethrough?: boolean;
	}

	const { name, value = $bindable(), strikethrough = false }: Props = $props();
</script>

{#snippet displayValue(value: unknown)}
	{#if Array.isArray(value)}
		<CodeblockArray {value} />
	{:else if value instanceof Object}
		<CodeblockObject {value} />
	{:else}
		<CodeblockLiteral {value} />
	{/if}
{/snippet}

<span class="line" style={strikethrough ? 'text-decoration: line-through;' : ''}
	><span style="color: var(--shiki-function)">{name}</span><span style="color: var(--shiki-keyword)"
		>&nbsp;=&nbsp;</span
	>{@render displayValue(value)}<span style="color: var(--shiki-punctuation)">;</span>
</span>
