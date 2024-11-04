<script lang="ts">
	import type { Snippet } from 'svelte';

	interface Props {
		name: string;
		children: Snippet;
	}

	const { name, children }: Props = $props();
</script>

<span class="line"
	><span style="color: var(--shiki-keyword)">class</span><span style="color: var(--shiki-parameter)"
		>&nbsp;{name}</span
	><span style="color: var(--shiki-punctuation)">&nbsp;&#123;</span></span
>{@render children()}
<br /><span class="line"><span style="color: var(--shiki-punctuation)">&#125;</span></span>
