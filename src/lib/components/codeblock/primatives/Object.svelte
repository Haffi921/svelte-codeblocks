<script lang="ts">
	interface Props {
		value: Object;
	}

	const { value }: Props = $props();
</script>

<span style="color: var(--shiki-punctuation)">&#123; </span>
{#each Object.entries(Object.entries(value)) as [index, [key, val]]}
	<span style="color: var(--shiki-punctuation)">{key}</span>:&nbsp;<span
		style="color: var(--shiki-constant)">{val}</span
	>{#if parseInt(index) < Object.entries(value).length - 1}<span
			style="color: var(--shiki-punctuation)">,&nbsp;</span
		>{/if}
{/each}
<span style="color: var(--shiki-punctuation)"> &#125;</span>
