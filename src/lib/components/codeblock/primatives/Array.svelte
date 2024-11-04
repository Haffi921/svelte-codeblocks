<script lang="ts">
	interface Props {
		value: unknown[];
	}

	const { value }: Props = $props();
</script>

<span style="color: var(--shiki-punctuation)">[ </span>
{#each value.entries() as [index, val]}
	<span style="color: var(--shiki-constant)">{val}</span>{#if index < value.length - 1}<span
			style="color: var(--shiki-punctuation)">,&nbsp;</span
		>{/if}
{/each}
<span style="color: var(--shiki-punctuation)"> ]</span>
